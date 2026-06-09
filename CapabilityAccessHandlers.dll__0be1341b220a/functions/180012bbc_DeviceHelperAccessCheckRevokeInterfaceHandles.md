# DeviceHelperAccessCheckRevokeInterfaceHandles

- ea: `0x180012bbc`
- end: `0x180012e95`
- name: `DeviceHelperAccessCheckRevokeInterfaceHandles`
- size: `729`
- prototype: `char __fastcall(__int64, const unsigned __int16 *, const WCHAR *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a1b0`
- `0x18000b6f0`
- `0x1800116c0`
- `0x180011be0`
- `0x180011c90`

## callees

- `0x180004c70`
- `0x18001248c`
- `0x18001260c`
- `0x180012bbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012e54`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180012cba`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180012cba`
- `ntdll!RtlInitUnicodeString` at `0x180012ca7`
- `ntdll!RtlInitUnicodeString` at `0x180012dc8`
- `ntdll!RtlInitUnicodeString` at `0x180012ca7`
- `ntdll!RtlInitUnicodeString` at `0x180012dc8`
- `ntdll!NtSetInformationProcess` at `0x180012de0`
- `ntdll!NtSetInformationProcess` at `0x180012de0`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180012cf8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180012cf8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180012e68`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180012e68`

## pseudocode

```c
char __fastcall DeviceHelperAccessCheckRevokeInterfaceHandles(__int64 a1, const unsigned __int16 *a2, const WCHAR *a3)
{
  __int64 *v4; // rax
  struct _SID *v6; // rbx
  unsigned __int16 ***p_SourceString; // rcx
  unsigned int v8; // r14d
  HANDLE *v9; // r15
  WCHAR *v10; // rdi
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // r14
  unsigned int v13; // esi
  __int64 v14; // r13
  _DWORD *v15; // rbx
  const unsigned __int16 *v16; // rdx
  const WCHAR *v17; // rax
  const WCHAR *v18; // rdx
  unsigned int i; // ebx
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v27; // [rsp+68h] [rbp-98h]
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-70h] BYREF
  DEVPROPKEY v31; // [rsp+98h] [rbp-68h]
  int v32; // [rsp+ACh] [rbp-54h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+BCh] [rbp-44h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  DEVPROPKEY v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+E4h] [rbp-1Ch]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  int v41; // [rsp+F0h] [rbp-10h]
  int v42; // [rsp+F4h] [rbp-Ch]
  __int64 *v43; // [rsp+F8h] [rbp-8h]
  _BYTE v44[48]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v45[48]; // [rsp+130h] [rbp+30h] BYREF

  v31 = DEVPKEY_DeviceInterface_ClassGuid;
  v38 = DEVPKEY_DeviceInterface_Enabled;
  v4 = &qword_1800177D0;
  v27 = a2;
  v21 = 0;
  v26 = 0;
  v22 = 0;
  hMem = 0;
  v25 = 0;
  SourceString = 0;
  v30 = 2;
  v32 = 0;
  v33 = 0;
  v34 = 13;
  v35 = 16;
  v36 = a1;
  v37 = 2;
  v39 = 0;
  v40 = 0;
  v41 = 17;
  v42 = 1;
  v43 = &qword_1800177D0;
  ProcessInformation = 0;
  if ( !a1 )
    return (char)v4;
  v6 = 0;
  if ( !a3 )
    goto LABEL_5;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  LODWORD(v4) = RtlDeriveCapabilitySidsFromName(&DestinationString, v45, v44);
  if ( (int)v4 >= 0 )
  {
    v6 = (struct _SID *)v44;
LABEL_5:
    LODWORD(v4) = DevGetObjects(1, 0, 0, 0, 2, &v30, &v21, &v26);
    if ( (int)v4 >= 0 )
    {
      p_SourceString = (unsigned __int16 ***)&SourceString;
      if ( a2 )
        p_SourceString = 0;
      LODWORD(v4) = _DeviceHelperGetProcessList(
                      (unsigned int)p_SourceString,
                      a3,
                      v6,
                      a2,
                      &v22,
                      (void ***)&hMem,
                      (unsigned int **)&v25,
                      p_SourceString);
      v8 = v22;
      v9 = (HANDLE *)hMem;
      v10 = (WCHAR *)SourceString;
      if ( (int)v4 >= 0 )
      {
        v11 = 0;
        LODWORD(hMem) = 0;
        if ( v22 )
        {
          do
          {
            if ( v21 )
            {
              v12 = v27;
              v13 = 0;
              v14 = v11;
              v15 = v25;
              do
              {
                v16 = v12;
                v17 = *(const WCHAR **)(32LL * v13 + v26 + 8);
                SourceString = v17;
                if ( !v12 )
                  v16 = *(const unsigned __int16 **)&v10[4 * v14];
                LOBYTE(v4) = _DeviceHelperAccessCheck(v15[v14], v16, v17, a3);
                if ( !(_BYTE)v4 )
                {
                  v18 = SourceString;
                  *((_WORD *)SourceString + 1) = 63;
                  RtlInitUnicodeString(&ProcessInformation, v18);
                  LOBYTE(v4) = NtSetInformationProcess(
                                 v9[v14],
                                 ProcessInstrumentationCallback|ProcessUserModeIOPL,
                                 &ProcessInformation,
                                 0x10u);
                }
                ++v13;
              }
              while ( v13 < v21 );
              v11 = (unsigned int)hMem;
              v8 = v22;
            }
            LODWORD(hMem) = ++v11;
          }
          while ( v11 < v8 );
        }
      }
      if ( v9 )
      {
        for ( i = 0; i < v8; ++i )
        {
          CloseHandle(v9[i]);
          if ( v10 )
            LocalFree(*(HLOCAL *)&v10[4 * i]);
        }
        LocalFree(v9);
        LOBYTE(v4) = (unsigned __int8)LocalFree(v25);
        if ( v10 )
          LOBYTE(v4) = (unsigned __int8)LocalFree(v10);
      }
    }
  }
  if ( v26 )
    LOBYTE(v4) = DevFreeObjects(v21);
  return (char)v4;
}

```

## disassembly

```asm
0x180012bbc  mov     [rsp-8+arg_18], rbx
0x180012bc1  push    rbp
0x180012bc2  push    rsi
0x180012bc3  push    rdi
0x180012bc4  push    r12
0x180012bc6  push    r13
0x180012bc8  push    r14
0x180012bca  push    r15
0x180012bcc  lea     rbp, [rsp-70h]
0x180012bd1  sub     rsp, 170h
0x180012bd8  mov     rax, cs:__security_cookie
0x180012bdf  xor     rax, rsp
0x180012be2  mov     [rbp+0A0h+var_40], rax
0x180012be6  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180012bec  xor     r13d, r13d
0x180012bef  mov     [rbp+0A0h+var_F8], eax
0x180012bf2  xorps   xmm0, xmm0
0x180012bf5  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180012bfb  mov     r12, r8
0x180012bfe  mov     [rbp+0A0h+var_C0], eax
0x180012c01  lea     rax, qword_1800177D0
0x180012c08  mov     [rsp+1A0h+var_138], rdx
0x180012c0d  lea     esi, [r13+2]
0x180012c11  mov     [rsp+1A0h+var_160], r13d
0x180012c16  mov     rdi, rdx
0x180012c19  mov     [rsp+1A0h+var_140], r13
0x180012c1e  mov     [rsp+1A0h+var_15C], r13d
0x180012c23  mov     [rsp+1A0h+hMem], r13
0x180012c28  mov     [rsp+1A0h+var_148], r13
0x180012c2d  mov     [rsp+1A0h+SourceString], r13
0x180012c32  mov     [rbp+0A0h+var_110], esi
0x180012c35  mov     [rbp+0A0h+var_F4], r13d
0x180012c39  mov     [rbp+0A0h+var_F0], r13
0x180012c3d  mov     [rbp+0A0h+var_E8], 0Dh
0x180012c44  mov     [rbp+0A0h+var_E4], 10h
0x180012c4b  mov     [rbp+0A0h+var_E0], rcx
0x180012c4f  mov     [rbp+0A0h+var_D8], esi
0x180012c52  mov     [rbp+0A0h+var_BC], r13d
0x180012c56  mov     [rbp+0A0h+var_B8], r13
0x180012c5a  mov     [rbp+0A0h+var_B0], 11h
0x180012c61  mov     [rbp+0A0h+var_AC], 1
0x180012c68  mov     [rbp+0A0h+var_A8], rax
0x180012c6c  movups  xmmword ptr [rbp+0A0h+ProcessInformation.Length], xmm0
0x180012c70  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180012c77  movups  [rbp+0A0h+var_108], xmm0
0x180012c7b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180012c82  movaps  [rbp+0A0h+var_D0], xmm0
0x180012c86  test    rcx, rcx
0x180012c89  jz      loc_180012E6E
0x180012c8f  mov     ebx, r13d
0x180012c92  test    r8, r8
0x180012c95  jz      short loc_180012CCC
0x180012c97  xorps   xmm0, xmm0
0x180012c9a  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x180012c9f  mov     rdx, r8; SourceString
0x180012ca2  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x180012ca7  call    cs:__imp_RtlInitUnicodeString
0x180012cad  lea     r8, [rbp+0A0h+var_A0]
0x180012cb1  lea     rdx, [rbp+0A0h+var_70]
0x180012cb5  lea     rcx, [rsp+1A0h+DestinationString]
0x180012cba  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180012cc0  test    eax, eax
0x180012cc2  js      loc_180012E5A
0x180012cc8  lea     rbx, [rbp+0A0h+var_A0]
0x180012ccc  lea     rax, [rsp+1A0h+var_140]
0x180012cd1  xor     edx, edx
0x180012cd3  mov     [rsp+1A0h+var_168], rax
0x180012cd8  xor     r9d, r9d
0x180012cdb  lea     rax, [rsp+1A0h+var_160]
0x180012ce0  xor     r8d, r8d
0x180012ce3  mov     [rsp+1A0h+var_170], rax
0x180012ce8  lea     rax, [rbp+0A0h+var_110]
0x180012cec  mov     [rsp+1A0h+var_178], rax
0x180012cf1  lea     ecx, [rdx+1]
0x180012cf4  mov     dword ptr [rsp+1A0h+var_180], esi
0x180012cf8  call    cs:__imp_DevGetObjects
0x180012cfe  test    eax, eax
0x180012d00  js      loc_180012E5A
0x180012d06  lea     rax, [rsp+1A0h+var_148]
0x180012d0b  test    rdi, rdi
0x180012d0e  lea     rcx, [rsp+1A0h+SourceString]
0x180012d13  mov     r9, rdi; unsigned __int16 *
0x180012d16  cmovnz  rcx, r13; unsigned int
0x180012d1a  mov     r8, rbx; struct _SID *
0x180012d1d  mov     [rsp+1A0h+var_168], rcx; unsigned __int16 ***
0x180012d22  mov     rdx, r12; unsigned __int16 *
0x180012d25  mov     [rsp+1A0h+var_170], rax; unsigned int **
0x180012d2a  lea     rax, [rsp+1A0h+hMem]
0x180012d2f  mov     [rsp+1A0h+var_178], rax; void ***
0x180012d34  lea     rax, [rsp+1A0h+var_15C]
0x180012d39  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x180012d3e  call    ?_DeviceHelperGetProcessList@@YAJKPEBGPEAU_SID@@0PEAKPEAPEAPEAXPEAPEAKPEAPEAPEAG@Z; _DeviceHelperGetProcessList(ulong,ushort const *,_SID *,ushort const *,ulong *,void * * *,ulong * *,ushort * * *)
0x180012d43  mov     r14d, [rsp+1A0h+var_15C]
0x180012d48  mov     r15, [rsp+1A0h+hMem]
0x180012d4d  mov     rdi, [rsp+1A0h+SourceString]
0x180012d52  test    eax, eax
0x180012d54  js      loc_180012E09
0x180012d5a  mov     ebx, r13d
0x180012d5d  mov     dword ptr [rsp+1A0h+hMem], ebx
0x180012d61  test    r14d, r14d
0x180012d64  jz      loc_180012E09
0x180012d6a  cmp     [rsp+1A0h+var_160], r13d
0x180012d6f  jbe     loc_180012DFA
0x180012d75  mov     r14, [rsp+1A0h+var_138]
0x180012d7a  mov     esi, r13d
0x180012d7d  mov     r13d, ebx
0x180012d80  mov     rbx, [rsp+1A0h+var_148]
0x180012d85  mov     rax, [rsp+1A0h+var_140]
0x180012d8a  mov     rdx, r14
0x180012d8d  mov     ecx, esi
0x180012d8f  shl     rcx, 5
0x180012d93  mov     rax, [rcx+rax+8]
0x180012d98  mov     [rsp+1A0h+SourceString], rax
0x180012d9d  test    r14, r14
0x180012da0  jnz     short loc_180012DA6
0x180012da2  mov     rdx, [rdi+r13*8]; unsigned __int16 *
0x180012da6  mov     ecx, [rbx+r13*4]; unsigned int
0x180012daa  mov     r9, r12; unsigned __int16 *
0x180012dad  mov     r8, rax; unsigned __int16 *
0x180012db0  call    ?_DeviceHelperAccessCheck@@YAEKPEBG00@Z; _DeviceHelperAccessCheck(ulong,ushort const *,ushort const *,ushort const *)
0x180012db5  test    al, al
0x180012db7  jnz     short loc_180012DE6
0x180012db9  mov     rdx, [rsp+1A0h+SourceString]; SourceString
0x180012dbe  lea     rcx, [rbp+0A0h+ProcessInformation]; DestinationString
0x180012dc2  mov     word ptr [rdx+2], 3Fh ; '?'
0x180012dc8  call    cs:__imp_RtlInitUnicodeString
0x180012dce  mov     rcx, [r15+r13*8]; ProcessHandle
0x180012dd2  lea     r8, [rbp+0A0h+ProcessInformation]; ProcessInformation
0x180012dd6  mov     r9d, 10h; ProcessInformationLength
0x180012ddc  lea     edx, [r9+28h]; ProcessInformationClass
0x180012de0  call    cs:__imp_NtSetInformationProcess
0x180012de6  inc     esi
0x180012de8  cmp     esi, [rsp+1A0h+var_160]
0x180012dec  jb      short loc_180012D85
0x180012dee  mov     ebx, dword ptr [rsp+1A0h+hMem]
0x180012df2  xor     r13d, r13d
0x180012df5  mov     r14d, [rsp+1A0h+var_15C]
0x180012dfa  inc     ebx
0x180012dfc  mov     dword ptr [rsp+1A0h+hMem], ebx
0x180012e00  cmp     ebx, r14d
0x180012e03  jb      loc_180012D6A
0x180012e09  test    r15, r15
0x180012e0c  jz      short loc_180012E5A
0x180012e0e  mov     ebx, r13d
0x180012e11  test    r14d, r14d
0x180012e14  jz      short loc_180012E38
0x180012e16  mov     esi, ebx
0x180012e18  mov     rcx, [r15+rsi*8]; hObject
0x180012e1c  call    cs:__imp_CloseHandle
0x180012e22  test    rdi, rdi
0x180012e25  jz      short loc_180012E31
0x180012e27  mov     rcx, [rdi+rsi*8]; hMem
0x180012e2b  call    cs:__imp_LocalFree
0x180012e31  inc     ebx
0x180012e33  cmp     ebx, r14d
0x180012e36  jb      short loc_180012E16
0x180012e38  mov     rcx, r15; hMem
0x180012e3b  call    cs:__imp_LocalFree
0x180012e41  mov     rcx, [rsp+1A0h+var_148]; hMem
0x180012e46  call    cs:__imp_LocalFree
0x180012e4c  test    rdi, rdi
0x180012e4f  jz      short loc_180012E5A
0x180012e51  mov     rcx, rdi; hMem
0x180012e54  call    cs:__imp_LocalFree
0x180012e5a  mov     rdx, [rsp+1A0h+var_140]
0x180012e5f  test    rdx, rdx
0x180012e62  jz      short loc_180012E6E
0x180012e64  mov     ecx, [rsp+1A0h+var_160]
0x180012e68  call    cs:__imp_DevFreeObjects
0x180012e6e  mov     rcx, [rbp+0A0h+var_40]
0x180012e72  xor     rcx, rsp; StackCookie
0x180012e75  call    __security_check_cookie
0x180012e7a  mov     rbx, [rsp+1A0h+arg_18]
0x180012e82  add     rsp, 170h
0x180012e89  pop     r15
0x180012e8b  pop     r14
0x180012e8d  pop     r13
0x180012e8f  pop     r12
0x180012e91  pop     rdi
0x180012e92  pop     rsi
0x180012e93  pop     rbp
0x180012e94  retn
```
