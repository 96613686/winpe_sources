# WsFindUse

- ea: `0x180009b80`
- end: `0x180009ee8`
- name: `WsFindUse`
- size: `872`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012a0`

## callees

- `0x1800024f0`
- `0x180004a40`
- `0x1800051c0`
- `0x180009b80`
- `0x180009ef0`
- `0x18001e420`
- `0x18002ed4c`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180009d7b`
- `ntdll!RtlCopyLuid` at `0x180009d7b`
- `ntdll!RtlCompareUnicodeString` at `0x180009c59`
- `ntdll!RtlCompareUnicodeString` at `0x180009c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009e2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009edb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009e2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009edb`

## pseudocode

```c
__int64 __fastcall WsFindUse(PLUID SourceLuid, __int64 *a2, WCHAR *a3, void **a4, _QWORD *a5, _QWORD *a6)
{
  __int64 *v8; // rdi
  __int64 *v9; // rsi
  WCHAR *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // r14
  __int64 result; // rax
  unsigned __int8 v15; // r12
  PHANDLE v16; // rcx
  __int64 v17; // r13
  __int64 v18; // r14
  BOOL v19; // edi
  unsigned __int16 *v20; // rax
  void *v21; // rsi
  unsigned int v22; // r13d
  unsigned __int16 *v23; // rcx
  DWORD ConnectionSpecifyImpersonation; // ebx
  UNICODE_STRING String1; // [rsp+90h] [rbp-80h] BYREF
  PHANDLE FileHandle; // [rsp+A0h] [rbp-70h]
  UNICODE_STRING String2; // [rsp+A8h] [rbp-68h] BYREF
  HLOCAL hMem[2]; // [rsp+B8h] [rbp-58h] BYREF
  _DWORD v29[2]; // [rsp+C8h] [rbp-48h] BYREF
  struct _LUID DestinationLuid[2]; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-30h]
  int v32; // [rsp+E8h] [rbp-28h]

  FileHandle = a4;
  v8 = a2;
  *(_QWORD *)&String1.Length = a5;
  v15 = *SourceLuid == -1;
  if ( a3[1] != 92 )
  {
    v9 = a2;
    while ( 1 )
    {
      if ( !v8 )
      {
        *a5 = 0;
        return 2250;
      }
      v10 = (WCHAR *)v8[2];
      if ( v10 )
      {
        String1 = 0;
        v11 = -1;
        String2 = 0;
        do
          ++v11;
        while ( v10[v11] );
        String1.Buffer = v10;
        String1.MaximumLength = 2 * (v11 + 1);
        String1.Length = String1.MaximumLength;
        v12 = -1;
        do
          ++v12;
        while ( a3[v12] );
        String2.Buffer = a3;
        String2.MaximumLength = 2 * (v12 + 1);
        String2.Length = String2.MaximumLength;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
          break;
      }
      v9 = v8;
      v8 = (__int64 *)*v8;
    }
    v16 = FileHandle;
    *a5 = v8;
    *v16 = (void *)v8[4];
    if ( a6 )
      *a6 = v9;
    return 0;
  }
  v13 = a2;
  while ( v8 )
  {
    if ( !v8[2] && !(unsigned int)FULLSTRICMP(v8[1] + 8, a3, a3) )
      goto LABEL_14;
    v13 = v8;
    v8 = (__int64 *)*v8;
  }
  v13 = 0;
  v8 = 0;
LABEL_14:
  **(_QWORD **)&String1.Length = v8;
  if ( v8 )
  {
    *FileHandle = (void *)v8[4];
    if ( a6 )
      *a6 = v13;
    return 0;
  }
  v31 = 0;
  v17 = -1;
  v32 = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v18 = -1;
  *(_QWORD *)&String1.Length = 0;
  do
    ++v18;
  while ( a3[v18] );
  v29[0] = 1;
  v29[1] = 6;
  *(_OWORD *)hMem = 0;
  RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, SourceLuid);
  DestinationLuid[0].LowPart = 0;
  v32 = 0;
  result = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, v29, 36, &String1, -1, 0);
  if ( !(_DWORD)result )
  {
    v19 = 0;
    v20 = *(unsigned __int16 **)&String1.Length;
    v21 = *(void **)&String1.Length;
    *(_QWORD *)&String2.Length = *(_QWORD *)&String1.Length;
    if ( DestinationLuid[1].HighPart )
    {
      v22 = 0;
      v23 = *(unsigned __int16 **)&String1.Length;
      do
      {
        if ( v19 )
          break;
        v19 = WsCompareStringU(*((_QWORD *)v23 + 1), *v20 >> 1, a3, (unsigned int)v18) == 0;
        v20 = (unsigned __int16 *)(*(_QWORD *)&String1.Length + 24LL);
        ++v22;
        *(_QWORD *)&String1.Length = v20;
        v23 = v20;
      }
      while ( v22 < DestinationLuid[1].HighPart );
      v21 = *(void **)&String2.Length;
      v17 = -1;
    }
    LocalFree(v21);
    if ( v19 )
    {
      do
        ++v17;
      while ( a3[v17] );
      result = WsCreateTreeConnectName((int)a3, v17, 0, v15, (PUNICODE_STRING)hMem);
      if ( !(_DWORD)result )
      {
        ConnectionSpecifyImpersonation = WsOpenCreateConnectionSpecifyImpersonation(
                                           (struct _UNICODE_STRING *)hMem,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           1u,
                                           -1,
                                           v15,
                                           1,
                                           0,
                                           FileHandle);
        LocalFree(hMem[1]);
        return ConnectionSpecifyImpersonation;
      }
    }
    else
    {
      return 2250;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009b80  push    rbp
0x180009b82  push    rbx
0x180009b83  push    rsi
0x180009b84  push    rdi
0x180009b85  push    r12
0x180009b87  push    r13
0x180009b89  push    r14
0x180009b8b  mov     rbp, rsp
0x180009b8e  sub     rsp, 110h
0x180009b95  mov     rax, cs:__security_cookie
0x180009b9c  xor     rax, rsp
0x180009b9f  mov     [rbp+var_20], rax
0x180009ba3  mov     r14, [rbp+arg_20]
0x180009ba7  mov     rsi, rcx
0x180009baa  mov     r13, [rbp+arg_28]
0x180009bae  xor     r12b, r12b
0x180009bb1  mov     [rbp+var_70], r9
0x180009bb5  mov     rbx, r8
0x180009bb8  mov     rdi, rdx
0x180009bbb  mov     qword ptr [rbp+String1.Length], r14
0x180009bbf  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x180009bc3  mov     ecx, 1
0x180009bc8  jz      loc_180009CDA
0x180009bce  cmp     word ptr [r8+2], 5Ch ; '\'
0x180009bd4  mov     [rsp+110h+var_8], r15
0x180009bdc  jz      loc_180009C79
0x180009be2  mov     rsi, rdi
0x180009be5  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009bec  nop     dword ptr [rax+00h]
0x180009bf0  test    rdi, rdi
0x180009bf3  jz      loc_180009D03
0x180009bf9  mov     rcx, [rdi+10h]
0x180009bfd  test    rcx, rcx
0x180009c00  jz      short loc_180009C6E
0x180009c02  xorps   xmm0, xmm0
0x180009c05  xorps   xmm1, xmm1
0x180009c08  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180009c0c  mov     rax, rdx
0x180009c0f  movups  xmmword ptr [rbp+String2.Length], xmm1
0x180009c13  inc     rax
0x180009c16  cmp     word ptr [rcx+rax*2], 0
0x180009c1b  jnz     short loc_180009C13
0x180009c1d  inc     ax
0x180009c20  mov     [rbp+String1.Buffer], rcx
0x180009c24  add     ax, ax
0x180009c27  mov     [rbp+String1.MaximumLength], ax
0x180009c2b  mov     [rbp+String1.Length], ax
0x180009c2f  mov     rax, rdx
0x180009c32  inc     rax
0x180009c35  cmp     word ptr [rbx+rax*2], 0
0x180009c3a  jnz     short loc_180009C32
0x180009c3c  inc     ax
0x180009c3f  mov     [rbp+String2.Buffer], rbx
0x180009c43  add     ax, ax
0x180009c46  lea     rdx, [rbp+String2]; String2
0x180009c4a  mov     r8b, 1; CaseInsensitive
0x180009c4d  mov     [rbp+String2.MaximumLength], ax
0x180009c51  lea     rcx, [rbp+String1]; String1
0x180009c55  mov     [rbp+String2.Length], ax
0x180009c59  call    cs:__imp_RtlCompareUnicodeString
0x180009c5f  test    eax, eax
0x180009c61  jz      loc_180009CEA
0x180009c67  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009c6e  mov     rsi, rdi
0x180009c71  mov     rdi, [rdi]
0x180009c74  jmp     loc_180009BF0
0x180009c79  mov     r14, rdi
0x180009c7c  xor     r15d, r15d
0x180009c7f  test    rdi, rdi
0x180009c82  jnz     loc_180009D0E
0x180009c88  mov     r14d, r15d
0x180009c8b  mov     edi, r15d
0x180009c8e  mov     rax, qword ptr [rbp+String1.Length]
0x180009c92  mov     [rax], rdi
0x180009c95  test    rdi, rdi
0x180009c98  jz      loc_180009D37
0x180009c9e  mov     rcx, [rbp+var_70]
0x180009ca2  mov     rax, [rdi+20h]
0x180009ca6  mov     [rcx], rax
0x180009ca9  test    r13, r13
0x180009cac  jz      short loc_180009CB2
0x180009cae  mov     [r13+0], r14
0x180009cb2  xor     eax, eax
0x180009cb4  mov     r15, [rsp+110h+var_8]
0x180009cbc  mov     rcx, [rbp+var_20]
0x180009cc0  xor     rcx, rsp; StackCookie
0x180009cc3  call    __security_check_cookie
0x180009cc8  add     rsp, 110h
0x180009ccf  pop     r14
0x180009cd1  pop     r13
0x180009cd3  pop     r12
0x180009cd5  pop     rdi
0x180009cd6  pop     rsi
0x180009cd7  pop     rbx
0x180009cd8  pop     rbp
0x180009cd9  retn
0x180009cda  cmp     dword ptr [rsi], 0FFFFFFFFh
0x180009cdd  movzx   r12d, r12b
0x180009ce1  cmovz   r12d, ecx
0x180009ce5  jmp     loc_180009BCE
0x180009cea  mov     rcx, [rbp+var_70]
0x180009cee  mov     [r14], rdi
0x180009cf1  mov     rax, [rdi+20h]
0x180009cf5  mov     [rcx], rax
0x180009cf8  test    r13, r13
0x180009cfb  jz      short loc_180009CB2
0x180009cfd  mov     [r13+0], rsi
0x180009d01  jmp     short loc_180009CB2
0x180009d03  xor     r15d, r15d
0x180009d06  mov     [r14], r15
0x180009d09  jmp     loc_180009E37
0x180009d0e  cmp     [rdi+10h], r15
0x180009d12  jnz     short loc_180009D2C
0x180009d14  mov     rcx, [rdi+8]
0x180009d18  mov     rdx, rbx
0x180009d1b  add     rcx, 8
0x180009d1f  call    FULLSTRICMP
0x180009d24  test    eax, eax
0x180009d26  jz      loc_180009C8E
0x180009d2c  mov     r14, rdi
0x180009d2f  mov     rdi, [rdi]
0x180009d32  jmp     loc_180009C7C
0x180009d37  xorps   xmm0, xmm0
0x180009d3a  mov     [rbp+var_30], r15
0x180009d3e  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180009d45  mov     [rbp+var_28], r15d
0x180009d49  movdqu  xmmword ptr [rbp+DestinationLuid.LowPart], xmm0
0x180009d4e  mov     r14, r13
0x180009d51  mov     qword ptr [rbp+String1.Length], r15
0x180009d55  inc     r14
0x180009d58  cmp     [rbx+r14*2], r15w
0x180009d5d  jnz     short loc_180009D55
0x180009d5f  xorps   xmm0, xmm0
0x180009d62  mov     [rbp+var_48], 1
0x180009d69  mov     rdx, rsi; SourceLuid
0x180009d6c  mov     [rbp+var_44], 6
0x180009d73  lea     rcx, [rbp+DestinationLuid.HighPart]; DestinationLuid
0x180009d77  movups  xmmword ptr [rbp+hMem], xmm0
0x180009d7b  call    cs:__imp_RtlCopyLuid
0x180009d81  mov     rdx, cs:WsRedirDeviceHandle
0x180009d88  lea     rax, [rbp+String1]
0x180009d8c  mov     dword ptr [rsp+110h+var_D8], r15d
0x180009d91  lea     r9, [rbp+var_48]
0x180009d95  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x180009d9d  mov     r8d, 1401A7h
0x180009da3  mov     [rsp+110h+var_E8], rax
0x180009da8  xor     ecx, ecx
0x180009daa  mov     dword ptr [rsp+110h+Destination], 24h ; '$'
0x180009db2  mov     [rbp+DestinationLuid.LowPart], r15d
0x180009db6  mov     [rbp+var_28], r15d
0x180009dba  call    WsDeviceControlGetInfo
0x180009dbf  test    eax, eax
0x180009dc1  jnz     loc_180009CB4
0x180009dc7  mov     edi, r15d
0x180009dca  mov     rax, qword ptr [rbp+String1.Length]
0x180009dce  mov     rsi, rax
0x180009dd1  mov     qword ptr [rbp+String2.Length], rax
0x180009dd5  cmp     [rbp+DestinationLuid.HighPart+8], r15d
0x180009dd9  jbe     short loc_180009E2A
0x180009ddb  mov     r13d, r15d
0x180009dde  mov     qword ptr [rbp+String1.Length], rax
0x180009de2  mov     rcx, rax
0x180009de5  mov     esi, 1
0x180009dea  test    edi, edi
0x180009dec  jnz     short loc_180009E1F
0x180009dee  movzx   edx, word ptr [rax]
0x180009df1  mov     r9d, r14d
0x180009df4  mov     rcx, [rcx+8]
0x180009df8  mov     r8, rbx
0x180009dfb  shr     edx, 1
0x180009dfd  call    WsCompareStringU
0x180009e02  test    eax, eax
0x180009e04  mov     rax, qword ptr [rbp+String1.Length]
0x180009e08  cmovz   edi, esi
0x180009e0b  add     rax, 18h
0x180009e0f  inc     r13d
0x180009e12  mov     qword ptr [rbp+String1.Length], rax
0x180009e16  mov     rcx, rax
0x180009e19  cmp     r13d, [rbp+DestinationLuid.HighPart+8]
0x180009e1d  jb      short loc_180009DEA
0x180009e1f  mov     rsi, qword ptr [rbp+String2.Length]
0x180009e23  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180009e2a  mov     rcx, rsi; hMem
0x180009e2d  call    cs:__imp_LocalFree
0x180009e33  test    edi, edi
0x180009e35  jnz     short loc_180009E41
0x180009e37  mov     eax, 8CAh
0x180009e3c  jmp     loc_180009CB4
0x180009e41  inc     r13
0x180009e44  cmp     [rbx+r13*2], r15w
0x180009e49  jnz     short loc_180009E41
0x180009e4b  lea     rax, [rbp+hMem]
0x180009e4f  movzx   r9d, r12b; int
0x180009e53  xor     r8d, r8d; int
0x180009e56  mov     [rsp+110h+Destination], rax; Destination
0x180009e5b  mov     edx, r13d; int
0x180009e5e  mov     rcx, rbx; int
0x180009e61  call    WsCreateTreeConnectName
0x180009e66  test    eax, eax
0x180009e68  jnz     loc_180009CB4
0x180009e6e  mov     rcx, [rbp+var_70]
0x180009e72  xor     r9d, r9d; int
0x180009e75  mov     [rsp+110h+var_88], r15
0x180009e7d  xor     r8d, r8d; int
0x180009e80  mov     [rsp+110h+FileHandle], rcx; FileHandle
0x180009e88  xor     edx, edx; int
0x180009e8a  mov     [rsp+110h+var_98], r15b; char
0x180009e8f  lea     rcx, [rbp+hMem]; int
0x180009e93  mov     [rsp+110h+var_A0], 1; char
0x180009e98  mov     [rsp+110h+var_A8], r12b; char
0x180009e9d  mov     [rsp+110h+var_B0], 0FFFFFFFFh; int
0x180009ea5  mov     [rsp+110h+var_B8], 1; ULONG
0x180009ead  mov     [rsp+110h+var_C0], r15d; ULONG
0x180009eb2  mov     [rsp+110h+var_C8], r15; __int64
0x180009eb7  mov     [rsp+110h+var_D0], r15; __int64
0x180009ebc  mov     [rsp+110h+var_D8], r15; __int64
0x180009ec1  mov     [rsp+110h+var_E0], r15; __int64
0x180009ec6  mov     [rsp+110h+var_E8], r15; hMem
0x180009ecb  mov     [rsp+110h+Destination], r15; __int64
0x180009ed0  call    WsOpenCreateConnectionSpecifyImpersonation
0x180009ed5  mov     rcx, [rbp+hMem+8]; hMem
0x180009ed9  mov     ebx, eax
0x180009edb  call    cs:__imp_LocalFree
0x180009ee1  mov     eax, ebx
0x180009ee3  jmp     loc_180009CB4
```
