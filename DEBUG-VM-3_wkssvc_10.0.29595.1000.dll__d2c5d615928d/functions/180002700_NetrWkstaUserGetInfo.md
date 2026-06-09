# NetrWkstaUserGetInfo

- ea: `0x180002700`
- end: `0x180002a52`
- name: `NetrWkstaUserGetInfo`
- size: `850`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002700`
- `0x180002a60`
- `0x1800051c0`
- `0x180005a60`
- `0x18001e420`
- `0x18001ed46`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x1800027bd`
- `ntdll!RtlCopyLuid` at `0x1800028a8`
- `ntdll!RtlCopyLuid` at `0x1800027bd`
- `ntdll!RtlCopyLuid` at `0x1800028a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000294f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000294f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000280f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000280f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a33`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800027f5`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800027f5`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002966`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002966`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserGetInfo(__int64 a1, unsigned int a2, char *a3)
{
  unsigned int v3; // r14d
  int v5; // r12d
  HLOCAL v6; // rsi
  __int64 result; // rax
  unsigned int v8; // r15d
  unsigned int v9; // r13d
  unsigned int v10; // eax
  unsigned int Info; // edi
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int i; // edx
  size_t v15; // r15
  char *v16; // rax
  char *v17; // rdi
  int v18; // r8d
  HLOCAL hMem; // [rsp+50h] [rbp-79h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-71h] BYREF
  ULONG ReturnBufferLength[2]; // [rsp+60h] [rbp-69h] BYREF
  struct _LUID SourceLuid; // [rsp+68h] [rbp-61h] BYREF
  char *v23; // [rsp+70h] [rbp-59h] BYREF
  int ProtocolSubmitBuffer; // [rsp+78h] [rbp-51h] BYREF
  _LUID DestinationLuid; // [rsp+7Ch] [rbp-4Dh] BYREF
  _DWORD v26[2]; // [rsp+90h] [rbp-39h] BYREF
  char v27[4]; // [rsp+98h] [rbp-31h] BYREF
  struct _LUID v28; // [rsp+9Ch] [rbp-2Dh] BYREF
  unsigned int v29; // [rsp+C8h] [rbp-1h]
  __int64 v30; // [rsp+D0h] [rbp+7h]

  v23 = a3;
  SourceLuid = 0;
  v3 = 8;
  Buffer = 0;
  v5 = 8;
  if ( a2 == 1 )
    v5 = 32;
  hMem = 0;
  v6 = 0;
  if ( a1 )
    return 87;
  if ( a2 > 1 && a2 != 1101 )
    return 124;
  result = WsImpersonateAndGetLogonId(&SourceLuid);
  if ( !(_DWORD)result )
  {
    ReturnBufferLength[0] = 0;
    if ( a2 != 1 )
    {
      v8 = 0;
      v9 = 0;
      if ( a2 != 1101 )
        goto LABEL_8;
    }
    memset_0(v27, 0, 0x58u);
    if ( WsDgReceiverDeviceHandle )
    {
      v26[1] = 6;
      v26[0] = 0;
      RtlCopyLuid(&v28, &SourceLuid);
      v30 = 0;
      Info = WsDeviceControlGetInfo(1, WsDgReceiverDeviceHandle, 1245207, v26, 96, &hMem, -1, 0);
      if ( Info )
        return Info;
      v9 = v29;
      v8 = 2;
      v6 = hMem;
      if ( v29 || !hMem )
      {
        for ( i = 0; i < v29; ++i )
        {
          if ( *((_DWORD *)hMem + 6 * i + 4) == 4 )
            v8 += *((unsigned __int16 *)hMem + 12 * i) + 2;
        }
      }
      else
      {
        LocalFree(hMem);
        v6 = 0;
      }
    }
    else
    {
      v9 = 0;
      v8 = 2;
    }
    if ( a2 == 1101 )
    {
      v13 = v8 + 8;
      if ( v8 + 8 >= v8 )
      {
LABEL_27:
        v15 = v13;
        v16 = (char *)LocalAlloc(0x40u, v13);
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, v15);
          v18 = (int)Buffer;
          *(_QWORD *)ReturnBufferLength = v17;
          *(_QWORD *)v23 = v17;
          v23 = &v17[v15];
          v3 = WsPackageUserInfo(a2, v5, v18, (_DWORD)v6, v9, (__int64)ReturnBufferLength, (__int64)&v23, 0);
        }
        if ( Buffer )
          LsaFreeReturnBuffer(Buffer);
        if ( v6 )
          LocalFree(v6);
        return v3;
      }
    }
    else
    {
LABEL_8:
      LODWORD(hMem) = 0;
      DestinationLuid = 0;
      ProtocolSubmitBuffer = 3;
      RtlCopyLuid(&DestinationLuid, &SourceLuid);
      v10 = LsaCallAuthenticationPackage(
              LsaHandle,
              AuthenticationPackage,
              &ProtocolSubmitBuffer,
              0xCu,
              &Buffer,
              ReturnBufferLength,
              (PNTSTATUS)&hMem);
      if ( v10 || (v10 = (unsigned int)hMem) != 0 )
      {
        Info = WsMapStatus(v10);
        if ( Info )
        {
          LocalFree(v6);
          return Info;
        }
      }
      if ( a2 )
        v12 = *((unsigned __int16 *)Buffer + 16)
            + *((unsigned __int16 *)Buffer + 24)
            + *((unsigned __int16 *)Buffer + 8)
            + 38;
      else
        v12 = *((unsigned __int16 *)Buffer + 8) + 10;
      v13 = v12 + v8;
      if ( v12 + v8 >= v8 )
        goto LABEL_27;
    }
    return 2140;
  }
  return result;
}

```

## disassembly

```asm
0x180002700  mov     [rsp-8+arg_18], rbx
0x180002705  push    rbp
0x180002706  push    rsi
0x180002707  push    rdi
0x180002708  push    r12
0x18000270a  push    r14
0x18000270c  lea     rbp, [rsp-37h]
0x180002711  sub     rsp, 100h
0x180002718  mov     rax, cs:__security_cookie
0x18000271f  xor     rax, rsp
0x180002722  mov     [rbp+57h+var_30], rax
0x180002726  xor     edi, edi
0x180002728  mov     [rbp+57h+var_B0], r8
0x18000272c  mov     qword ptr [rbp+57h+SourceLuid.LowPart], rdi
0x180002730  mov     r14d, 8
0x180002736  mov     [rbp+57h+Buffer], rdi
0x18000273a  mov     ebx, edx
0x18000273c  mov     r12d, r14d
0x18000273f  test    edx, edx
0x180002741  jz      short loc_18000274F
0x180002743  cmp     edx, 1
0x180002746  mov     eax, 20h ; ' '
0x18000274b  cmovz   r12d, eax
0x18000274f  mov     [rbp+57h+hMem], rdi
0x180002753  mov     rsi, rdi
0x180002756  test    rcx, rcx
0x180002759  jnz     loc_180002995
0x18000275f  cmp     ebx, 1
0x180002762  ja      loc_180002A03
0x180002768  lea     rcx, [rbp+57h+SourceLuid]; DestinationLuid
0x18000276c  call    WsImpersonateAndGetLogonId
0x180002771  test    eax, eax
0x180002773  jnz     loc_180002855
0x180002779  mov     [rsp+120h+arg_0], r13
0x180002781  mov     [rsp+120h+arg_8], r15
0x180002789  mov     [rbp+57h+var_C0], edi
0x18000278c  cmp     ebx, 1
0x18000278f  jz      loc_180002878
0x180002795  mov     r15d, edi
0x180002798  mov     r13d, edi
0x18000279b  cmp     ebx, 44Dh
0x1800027a1  jz      loc_180002878
0x1800027a7  lea     rdx, [rbp+57h+SourceLuid]; SourceLuid
0x1800027ab  mov     dword ptr [rbp+57h+hMem], edi
0x1800027ae  lea     rcx, [rbp+57h+DestinationLuid]; DestinationLuid
0x1800027b2  mov     qword ptr [rbp+57h+DestinationLuid.LowPart], rdi
0x1800027b6  mov     [rbp+57h+ProtocolSubmitBuffer], 3
0x1800027bd  call    cs:__imp_RtlCopyLuid
0x1800027c3  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x1800027c9  lea     rax, [rbp+57h+hMem]
0x1800027cd  mov     rcx, cs:LsaHandle; LsaHandle
0x1800027d4  lea     r8, [rbp+57h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x1800027d8  mov     [rsp+120h+ProtocolStatus], rax; ProtocolStatus
0x1800027dd  mov     r9d, 0Ch; SubmitBufferLength
0x1800027e3  lea     rax, [rbp+57h+var_C0]
0x1800027e7  mov     [rsp+120h+ReturnBufferLength], rax; ReturnBufferLength
0x1800027ec  lea     rax, [rbp+57h+Buffer]
0x1800027f0  mov     [rsp+120h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x1800027f5  call    cs:__imp_LsaCallAuthenticationPackage
0x1800027fb  test    eax, eax
0x1800027fd  jz      short loc_180002817
0x1800027ff  mov     ecx, eax
0x180002801  call    WsMapStatus
0x180002806  mov     edi, eax
0x180002808  test    eax, eax
0x18000280a  jz      short loc_18000281E
0x18000280c  mov     rcx, rsi; hMem
0x18000280f  call    cs:__imp_LocalFree
0x180002815  jmp     short loc_180002843
0x180002817  mov     eax, dword ptr [rbp+57h+hMem]
0x18000281a  test    eax, eax
0x18000281c  jnz     short loc_1800027FF
0x18000281e  test    ebx, ebx
0x180002820  jnz     loc_180002979
0x180002826  mov     rax, [rbp+57h+Buffer]
0x18000282a  movzx   ecx, word ptr [rax+10h]
0x18000282e  add     ecx, 0Ah
0x180002831  lea     eax, [rcx+r15]
0x180002835  cmp     eax, r15d
0x180002838  jnb     loc_180002945
0x18000283e  mov     edi, 85Ch
0x180002843  mov     eax, edi
0x180002845  mov     r13, [rsp+120h+arg_0]
0x18000284d  mov     r15, [rsp+120h+arg_8]
0x180002855  mov     rcx, [rbp+57h+var_30]
0x180002859  xor     rcx, rsp; StackCookie
0x18000285c  call    __security_check_cookie
0x180002861  mov     rbx, [rsp+120h+arg_18]
0x180002869  add     rsp, 100h
0x180002870  pop     r14
0x180002872  pop     r12
0x180002874  pop     rdi
0x180002875  pop     rsi
0x180002876  pop     rbp
0x180002877  retn
0x180002878  xor     edx, edx; Val
0x18000287a  lea     rcx, [rbp+57h+var_88]; void *
0x18000287e  mov     r8d, 58h ; 'X'; Size
0x180002884  call    memset_0
0x180002889  cmp     cs:WsDgReceiverDeviceHandle, rdi
0x180002890  jz      loc_180002A19
0x180002896  lea     rdx, [rbp+57h+SourceLuid]; SourceLuid
0x18000289a  mov     [rbp+57h+var_8C], 6
0x1800028a1  lea     rcx, [rbp+57h+var_84]; DestinationLuid
0x1800028a5  mov     [rbp+57h+var_90], edi
0x1800028a8  call    cs:__imp_RtlCopyLuid
0x1800028ae  mov     rdx, cs:WsDgReceiverDeviceHandle
0x1800028b5  lea     rax, [rbp+57h+hMem]
0x1800028b9  mov     dword ptr [rsp+120h+var_E8], edi
0x1800028bd  lea     r9, [rbp+57h+var_90]
0x1800028c1  mov     dword ptr [rsp+120h+ProtocolStatus], 0FFFFFFFFh
0x1800028c9  mov     r8d, 130017h
0x1800028cf  mov     [rsp+120h+ReturnBufferLength], rax
0x1800028d4  mov     ecx, 1
0x1800028d9  mov     dword ptr [rsp+120h+ProtocolReturnBuffer], 60h ; '`'
0x1800028e1  mov     [rbp+57h+var_50], rdi
0x1800028e5  call    WsDeviceControlGetInfo
0x1800028ea  mov     edi, eax
0x1800028ec  test    eax, eax
0x1800028ee  jnz     loc_180002843
0x1800028f4  mov     r13d, [rbp+57h+var_58]
0x1800028f8  mov     r15d, 2
0x1800028fe  mov     rsi, [rbp+57h+hMem]
0x180002902  test    r13d, r13d
0x180002905  jz      loc_180002A27
0x18000290b  xor     edi, edi
0x18000290d  mov     edx, edi
0x18000290f  test    r13d, r13d
0x180002912  jz      short loc_18000292C
0x180002914  mov     eax, edx
0x180002916  lea     rcx, [rax+rax*2]
0x18000291a  cmp     dword ptr [rsi+rcx*8+10h], 4
0x18000291f  jz      loc_180002A42
0x180002925  inc     edx
0x180002927  cmp     edx, r13d
0x18000292a  jb      short loc_180002914
0x18000292c  cmp     ebx, 44Dh
0x180002932  jnz     loc_1800027A7
0x180002938  lea     eax, [r15+8]
0x18000293c  cmp     eax, r15d
0x18000293f  jb      loc_18000283E
0x180002945  mov     edx, eax; uBytes
0x180002947  mov     ecx, 40h ; '@'; uFlags
0x18000294c  mov     r15d, eax
0x18000294f  call    cs:__imp_LocalAlloc
0x180002955  mov     rdi, rax
0x180002958  test    rax, rax
0x18000295b  jnz     short loc_1800029AA
0x18000295d  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180002961  test    rcx, rcx
0x180002964  jz      short loc_18000296C
0x180002966  call    cs:__imp_LsaFreeReturnBuffer
0x18000296c  test    rsi, rsi
0x18000296f  jnz     short loc_18000299F
0x180002971  mov     eax, r14d
0x180002974  jmp     loc_180002845
0x180002979  mov     rcx, [rbp+57h+Buffer]
0x18000297d  movzx   edx, word ptr [rcx+30h]
0x180002981  movzx   eax, word ptr [rcx+20h]
0x180002985  movzx   ecx, word ptr [rcx+10h]
0x180002989  add     edx, eax
0x18000298b  add     ecx, 26h ; '&'
0x18000298e  add     ecx, edx
0x180002990  jmp     loc_180002831
0x180002995  mov     eax, 57h ; 'W'
0x18000299a  jmp     loc_180002855
0x18000299f  mov     rcx, rsi; hMem
0x1800029a2  call    cs:__imp_LocalFree
0x1800029a8  jmp     short loc_180002971
0x1800029aa  mov     r8, r15; Size
0x1800029ad  xor     edx, edx; Val
0x1800029af  mov     rcx, rdi; void *
0x1800029b2  call    memset_0
0x1800029b7  mov     rax, [rbp+57h+var_B0]
0x1800029bb  mov     r9, rsi
0x1800029be  mov     r8, [rbp+57h+Buffer]
0x1800029c2  mov     edx, r12d
0x1800029c5  mov     [rsp+120h+var_E8], 0
0x1800029ce  mov     ecx, ebx
0x1800029d0  mov     qword ptr [rbp+57h+var_C0], rdi
0x1800029d4  mov     [rax], rdi
0x1800029d7  lea     rax, [r15+rdi]
0x1800029db  mov     [rbp+57h+var_B0], rax
0x1800029df  lea     rax, [rbp+57h+var_B0]
0x1800029e3  mov     [rsp+120h+ProtocolStatus], rax
0x1800029e8  lea     rax, [rbp+57h+var_C0]
0x1800029ec  mov     [rsp+120h+ReturnBufferLength], rax
0x1800029f1  mov     dword ptr [rsp+120h+ProtocolReturnBuffer], r13d
0x1800029f6  call    WsPackageUserInfo
0x1800029fb  mov     r14d, eax
0x1800029fe  jmp     loc_18000295D
0x180002a03  cmp     ebx, 44Dh
0x180002a09  jz      loc_180002768
0x180002a0f  mov     eax, 7Ch ; '|'
0x180002a14  jmp     loc_180002855
0x180002a19  mov     r13d, edi
0x180002a1c  mov     r15d, 2
0x180002a22  jmp     loc_18000292C
0x180002a27  test    rsi, rsi
0x180002a2a  jz      loc_18000290B
0x180002a30  mov     rcx, rsi; hMem
0x180002a33  call    cs:__imp_LocalFree
0x180002a39  xor     edi, edi
0x180002a3b  mov     esi, edi
0x180002a3d  jmp     loc_18000292C
0x180002a42  movzx   eax, word ptr [rsi+rcx*8]
0x180002a46  add     r15d, 2
0x180002a4a  add     r15d, eax
0x180002a4d  jmp     loc_180002925
```
