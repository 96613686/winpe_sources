# USBSTOR_SenseDataCompletionRoutine

- ea: `0x140009cb0`
- end: `0x140009f81`
- name: `USBSTOR_SenseDataCompletionRoutine`
- size: `721`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140003630`
- `0x140004910`
- `0x140009cb0`
- `0x140009f90`
- `0x14000fafc`
- `0x14000fd74`
- `0x1400104c8`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140013a40`

## pseudocode

```c
__int64 __fastcall USBSTOR_SenseDataCompletionRoutine(_QWORD *a1, IRP *a2, __int64 a3)
{
  _DWORD *v6; // rbx
  void *v7; // rbp
  __int64 SecurityContext; // r14
  __int64 v10; // r8
  __int64 Status; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  size_t v14; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1380140115, a1, a2, a2->IoStatus.Status);
  v6 = (_DWORD *)a1[8];
  if ( *v6 == 558842960 )
  {
    a1 = (_QWORD *)*((_QWORD *)v6 + 2);
    v7 = v6;
    v6 = (_DWORD *)a1[8];
  }
  else
  {
    v7 = 0;
    if ( *v6 != 558842950 )
    {
      v6 = 0;
      a1 = 0;
    }
  }
  SecurityContext = (__int64)a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( (unsigned __int8)USBSTOR_CheckRequestTimeOut(a1) )
  {
    USBSTOR_LogEntry(828597363, a1, a2, SecurityContext);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 0;
  }
  else
  {
    v10 = (int)v6[99];
    Status = a2->IoStatus.Status;
    if ( (int)Status >= 0 )
    {
      USBSTOR_LogEntry(862151795, Status, v10, (unsigned int)v6[107]);
      if ( !a3 )
      {
        v13 = v6[107];
        v14 = 18;
        if ( v13 < 0x12 )
          v14 = v13;
        memmove((char *)v6 + 1206, *((const void **)v6 + 54), v14);
        *(_BYTE *)(SecurityContext + 11) = *((_BYTE *)v6 + 428);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 126);
      }
      if ( *((_QWORD *)v6 + 14) )
      {
        USBSTOR_IssueRequestSenseInterruptRequest(a1, a2, a3);
        v12 = -1073741802;
      }
      else
      {
        v12 = USBSTOR_ProcessRequestSenseCompletion(a1, a2);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
    }
    else
    {
      USBSTOR_LogEntry(845374579, Status, v10, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          124,
          WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          (unsigned int)a2->IoStatus.Status,
          v6[99]);
      }
      a2->IoStatus.Information = 0;
      v12 = -1073741435;
      a2->IoStatus.Status = -1073741435;
      *(_BYTE *)(SecurityContext + 3) = 14;
      USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
      USBSTOR_QueueResetDevice(a1, v7);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
    }
    return v12;
  }
}

```

## disassembly

```asm
0x140009cb0  push    rbx
0x140009cb2  push    rbp
0x140009cb3  push    rsi
0x140009cb4  push    rdi
0x140009cb5  push    r14
0x140009cb7  push    r15
0x140009cb9  sub     rsp, 38h
0x140009cbd  mov     r15, r8
0x140009cc0  mov     [rsp+68h+arg_0], 0
0x140009cc8  mov     rsi, rdx
0x140009ccb  mov     rdi, rcx
0x140009cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140009cd5  lea     rax, WPP_GLOBAL_Control
0x140009cdc  cmp     rcx, rax
0x140009cdf  jz      short loc_140009D03
0x140009ce1  mov     eax, [rcx+2Ch]
0x140009ce4  test    al, 1
0x140009ce6  jz      short loc_140009D03
0x140009ce8  cmp     byte ptr [rcx+29h], 5
0x140009cec  jb      short loc_140009D03
0x140009cee  mov     rcx, [rcx+18h]
0x140009cf2  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009cf9  mov     edx, 7Ah ; 'z'
0x140009cfe  call    WPP_SF_
0x140009d03  movsxd  r9, dword ptr [rsi+30h]
0x140009d07  mov     r8, rsi
0x140009d0a  mov     rdx, rdi
0x140009d0d  mov     ecx, 52434453h
0x140009d12  call    USBSTOR_LogEntry
0x140009d17  mov     rbx, [rdi+40h]
0x140009d1b  mov     eax, [rbx]
0x140009d1d  cmp     eax, 214F4450h
0x140009d22  jnz     short loc_140009D31
0x140009d24  mov     rdi, [rbx+10h]
0x140009d28  mov     rbp, rbx
0x140009d2b  mov     rbx, [rdi+40h]
0x140009d2f  jmp     short loc_140009D3E
0x140009d31  xor     ebp, ebp
0x140009d33  cmp     eax, 214F4446h
0x140009d38  jz      short loc_140009D3E
0x140009d3a  xor     ebx, ebx
0x140009d3c  xor     edi, edi
0x140009d3e  mov     rax, [rsi+0B8h]
0x140009d45  lea     r9, [rsp+68h+arg_0]
0x140009d4a  mov     rdx, rsi
0x140009d4d  mov     rcx, rdi; Object
0x140009d50  mov     r14, [rax+8]
0x140009d54  mov     r8, r14
0x140009d57  call    USBSTOR_CheckRequestTimeOut
0x140009d5c  test    al, al
0x140009d5e  jz      short loc_140009DB1
0x140009d60  mov     r9, r14
0x140009d63  mov     r8, rsi
0x140009d66  mov     rdx, rdi
0x140009d69  mov     ecx, 31636473h
0x140009d6e  call    USBSTOR_LogEntry
0x140009d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d7a  lea     r15, WPP_GLOBAL_Control
0x140009d81  cmp     rcx, r15
0x140009d84  jz      short loc_140009DA8
0x140009d86  mov     eax, [rcx+2Ch]
0x140009d89  test    al, 1
0x140009d8b  jz      short loc_140009DA8
0x140009d8d  cmp     byte ptr [rcx+29h], 2
0x140009d91  jb      short loc_140009DA8
0x140009d93  mov     rcx, [rcx+18h]
0x140009d97  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009d9e  mov     edx, 7Bh ; '{'
0x140009da3  call    WPP_SF_
0x140009da8  mov     eax, [rsp+68h+arg_0]
0x140009dac  jmp     loc_140009F73
0x140009db1  movsxd  rax, dword ptr [rsi+30h]
0x140009db5  movsxd  r8, dword ptr [rbx+18Ch]
0x140009dbc  mov     rdx, rax
0x140009dbf  test    eax, eax
0x140009dc1  jns     loc_140009E85
0x140009dc7  xor     r9d, r9d
0x140009dca  mov     ecx, 32636473h
0x140009dcf  call    USBSTOR_LogEntry
0x140009dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ddb  lea     r15, WPP_GLOBAL_Control
0x140009de2  cmp     rcx, r15
0x140009de5  jz      short loc_140009E17
0x140009de7  mov     eax, [rcx+2Ch]
0x140009dea  test    al, 1
0x140009dec  jz      short loc_140009E17
0x140009dee  cmp     byte ptr [rcx+29h], 2
0x140009df2  jb      short loc_140009E17
0x140009df4  mov     eax, [rbx+18Ch]
0x140009dfa  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009e01  mov     r9d, [rsi+30h]
0x140009e05  mov     edx, 7Ch ; '|'
0x140009e0a  mov     rcx, [rcx+18h]
0x140009e0e  mov     [rsp+68h+var_48], eax
0x140009e12  call    WPP_SF_DD
0x140009e17  mov     qword ptr [rsi+38h], 0
0x140009e1f  mov     ebx, 0C0000185h
0x140009e24  mov     [rsi+30h], ebx
0x140009e27  mov     r8, r14
0x140009e2a  mov     rdx, rsi
0x140009e2d  mov     byte ptr [r14+3], 0Eh
0x140009e32  mov     rcx, rdi; Object
0x140009e35  call    USBSTOR_TranslateCDBComplete
0x140009e3a  mov     rdx, rbp; Context
0x140009e3d  mov     rcx, rdi; Object
0x140009e40  call    USBSTOR_QueueResetDevice
0x140009e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e4c  cmp     rcx, r15
0x140009e4f  jz      loc_140009F71
0x140009e55  mov     edx, [rcx+2Ch]
0x140009e58  test    dl, 1
0x140009e5b  jz      loc_140009F71
0x140009e61  cmp     byte ptr [rcx+29h], 2
0x140009e65  jb      loc_140009F71
0x140009e6b  mov     rcx, [rcx+18h]
0x140009e6f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009e76  mov     edx, 7Dh ; '}'
0x140009e7b  call    WPP_SF_
0x140009e80  jmp     loc_140009F71
0x140009e85  mov     r9d, [rbx+1ACh]
0x140009e8c  mov     ecx, 33636473h
0x140009e91  call    USBSTOR_LogEntry
0x140009e96  test    r15, r15
0x140009e99  jnz     short loc_140009ECA
0x140009e9b  mov     eax, [rbx+1ACh]
0x140009ea1  lea     r8d, [r15+12h]
0x140009ea5  cmp     eax, r8d
0x140009ea8  jnb     short loc_140009EAD
0x140009eaa  mov     r8d, eax; Size
0x140009ead  mov     rdx, [rbx+1B0h]; Src
0x140009eb4  lea     rcx, [rbx+4B6h]; void *
0x140009ebb  call    memmove
0x140009ec0  mov     al, [rbx+1ACh]
0x140009ec6  mov     [r14+0Bh], al
0x140009eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ed1  lea     rbp, WPP_GLOBAL_Control
0x140009ed8  cmp     rcx, rbp
0x140009edb  jz      short loc_140009F1C
0x140009edd  mov     eax, [rcx+2Ch]
0x140009ee0  test    al, 1
0x140009ee2  jz      short loc_140009F1C
0x140009ee4  cmp     byte ptr [rcx+29h], 4
0x140009ee8  jb      short loc_140009F1C
0x140009eea  movzx   eax, byte ptr [rbx+4C3h]
0x140009ef1  mov     edx, 7Eh ; '~'
0x140009ef6  movzx   r9d, byte ptr [rbx+4B8h]
0x140009efe  movzx   r8d, byte ptr [rbx+4C2h]
0x140009f06  and     r9d, 0Fh
0x140009f0a  mov     rcx, [rcx+18h]
0x140009f0e  mov     [rsp+68h+var_40], eax
0x140009f12  mov     [rsp+68h+var_48], r8d
0x140009f17  call    WPP_SF_DDD
0x140009f1c  cmp     qword ptr [rbx+70h], 0
0x140009f21  mov     r8, r15; __int64
0x140009f24  mov     rdx, rsi; Irp
0x140009f27  mov     rcx, rdi; Object
0x140009f2a  jz      short loc_140009F38
0x140009f2c  call    USBSTOR_IssueRequestSenseInterruptRequest
0x140009f31  mov     ebx, 0C0000016h
0x140009f36  jmp     short loc_140009F3F
0x140009f38  call    USBSTOR_ProcessRequestSenseCompletion
0x140009f3d  mov     ebx, eax
0x140009f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f46  cmp     rcx, rbp
0x140009f49  jz      short loc_140009F71
0x140009f4b  mov     edx, [rcx+2Ch]
0x140009f4e  test    dl, 1
0x140009f51  jz      short loc_140009F71
0x140009f53  cmp     byte ptr [rcx+29h], 5
0x140009f57  jb      short loc_140009F71
0x140009f59  mov     rcx, [rcx+18h]
0x140009f5d  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009f64  mov     edx, 7Fh
0x140009f69  mov     r9d, ebx
0x140009f6c  call    WPP_SF_d
0x140009f71  mov     eax, ebx
0x140009f73  add     rsp, 38h
0x140009f77  pop     r15
0x140009f79  pop     r14
0x140009f7b  pop     rdi
0x140009f7c  pop     rsi
0x140009f7d  pop     rbp
0x140009f7e  pop     rbx
0x140009f7f  retn
```
