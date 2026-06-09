# Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001ec60`
- end: `0x18001ede3`
- name: `?OnAfterEvents@CNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `387`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001ec60`
- `0x180026e30`
- `0x180026f6c`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001ecb6`
- `KERNEL32!GetProcAddress` at `0x18001ecd2`
- `KERNEL32!GetProcAddress` at `0x18001ecb6`
- `KERNEL32!GetProcAddress` at `0x18001ecd2`
- `KERNEL32!FreeLibrary` at `0x18001edbb`
- `KERNEL32!FreeLibrary` at `0x18001edbb`
- `KERNEL32!LoadLibraryExW` at `0x18001eca3`
- `KERNEL32!LoadLibraryExW` at `0x18001eca3`

## string_xrefs

- `0x18001ec97`: `Iphlpapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v7; // esi
  HMODULE Library; // r14
  FARPROC ProcAddress; // rdi
  FARPROC v10; // r15
  _DWORD *v11; // rdi
  int v12; // esi
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rcx
  _DWORD *v18; // [rsp+38h] [rbp-61h] BYREF
  _WORD v19[2]; // [rsp+40h] [rbp-59h] BYREF
  char v20; // [rsp+44h] [rbp-55h]
  union _LARGE_INTEGER v21; // [rsp+50h] [rbp-49h]
  __int128 v22; // [rsp+58h] [rbp-41h]
  _DWORD *v23; // [rsp+88h] [rbp-11h]
  int v24; // [rsp+90h] [rbp-9h]
  unsigned int v25; // [rsp+94h] [rbp-5h]

  v7 = a4;
  Library = LoadLibraryExW(L"Iphlpapi.dll", 0, 0);
  ProcAddress = GetProcAddress(Library, "GetIfTable2Ex");
  if ( !ProcAddress )
    goto LABEL_8;
  v10 = GetProcAddress(Library, "FreeMibTable");
  if ( !v10 || ((unsigned int (__fastcall *)(_QWORD, _DWORD **))ProcAddress)(0, &v18) )
    goto LABEL_8;
  v11 = v18;
  v12 = 0;
  if ( !*v18 )
  {
LABEL_7:
    ((void (__fastcall *)(_DWORD *))v10)(v11);
    v7 = a4;
LABEL_8:
    v15 = *((_QWORD *)this + 1);
    if ( v15 )
      v14 = (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v15 + 96LL))(
              v15,
              a2,
              a3,
              v7);
    else
      v14 = 1;
    goto LABEL_11;
  }
  while ( 1 )
  {
    memset_0(v19, 0, 0x58u);
    v13 = *((_QWORD *)this + 2);
    v19[0] = a4;
    v21 = a2;
    v22 = SystemConfigExGuid;
    v20 = 36;
    v24 = 1352;
    v25 = a3;
    v23 = &v11[338 * v12 + 2];
    v14 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v13 + 192LL))(v13, v19, 0, 0);
    if ( v14 < 0 )
      break;
    v11 = v18;
    if ( (unsigned int)++v12 >= *v18 )
      goto LABEL_7;
  }
LABEL_11:
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001ec60  push    rbp
0x18001ec62  push    rbx
0x18001ec63  push    rsi
0x18001ec64  push    rdi
0x18001ec65  push    r12
0x18001ec67  push    r13
0x18001ec69  push    r14
0x18001ec6b  push    r15
0x18001ec6d  lea     rbp, [rsp-1Fh]
0x18001ec72  sub     rsp, 0B8h
0x18001ec79  mov     rax, cs:__security_cookie
0x18001ec80  xor     rax, rsp
0x18001ec83  mov     [rbp+57h+var_50], rax
0x18001ec87  mov     r12d, r8d
0x18001ec8a  mov     [rbp+57h+var_C0], r9d
0x18001ec8e  mov     rbx, rdx
0x18001ec91  mov     r13, rcx
0x18001ec94  xor     r8d, r8d; dwFlags
0x18001ec97  lea     rcx, aIphlpapiDll; "Iphlpapi.dll"
0x18001ec9e  xor     edx, edx; hFile
0x18001eca0  mov     esi, r9d
0x18001eca3  call    cs:__imp_LoadLibraryExW
0x18001eca9  mov     rcx, rax; hModule
0x18001ecac  lea     rdx, aGetiftable2ex; "GetIfTable2Ex"
0x18001ecb3  mov     r14, rax
0x18001ecb6  call    cs:__imp_GetProcAddress
0x18001ecbc  mov     rdi, rax
0x18001ecbf  test    rax, rax
0x18001ecc2  jz      loc_18001ED8B
0x18001ecc8  lea     rdx, aFreemibtable; "FreeMibTable"
0x18001eccf  mov     rcx, r14; hModule
0x18001ecd2  call    cs:__imp_GetProcAddress
0x18001ecd8  mov     r15, rax
0x18001ecdb  test    rax, rax
0x18001ecde  jz      loc_18001ED8B
0x18001ece4  lea     rdx, [rbp+57h+var_B8]
0x18001ece8  xor     ecx, ecx
0x18001ecea  mov     rax, rdi
0x18001eced  call    cs:__guard_dispatch_icall_fptr
0x18001ecf3  test    eax, eax
0x18001ecf5  jnz     loc_18001ED8B
0x18001ecfb  mov     rdi, [rbp+57h+var_B8]
0x18001ecff  xor     esi, esi
0x18001ed01  cmp     [rdi], esi
0x18001ed03  jbe     short loc_18001ED7C
0x18001ed05  xor     edx, edx; Val
0x18001ed07  lea     rcx, [rbp+57h+var_B0]; void *
0x18001ed0b  lea     r8d, [rdx+58h]; Size
0x18001ed0f  call    memset_0
0x18001ed14  mov     eax, [rbp+57h+var_C0]
0x18001ed17  lea     rdx, [rbp+57h+var_B0]
0x18001ed1b  movups  xmm0, cs:SystemConfigExGuid
0x18001ed22  mov     rcx, [r13+10h]
0x18001ed26  xor     r9d, r9d
0x18001ed29  mov     [rbp+57h+var_B0], ax
0x18001ed2d  xor     r8d, r8d
0x18001ed30  mov     [rbp+57h+var_A0], rbx
0x18001ed34  movdqu  [rbp+57h+var_98], xmm0
0x18001ed39  mov     [rbp+57h+var_AC], 24h ; '$'
0x18001ed3d  mov     [rbp+57h+var_60], 548h
0x18001ed44  mov     [rbp+57h+var_5C], r12d
0x18001ed48  mov     eax, esi
0x18001ed4a  imul    rax, 548h
0x18001ed51  add     rax, 8
0x18001ed55  add     rax, rdi
0x18001ed58  mov     [rbp+57h+var_68], rax
0x18001ed5c  mov     rax, [rcx]
0x18001ed5f  mov     rax, [rax+0C0h]
0x18001ed66  call    cs:__guard_dispatch_icall_fptr
0x18001ed6c  mov     edi, eax
0x18001ed6e  test    eax, eax
0x18001ed70  js      short loc_18001EDB3
0x18001ed72  mov     rdi, [rbp+57h+var_B8]
0x18001ed76  inc     esi
0x18001ed78  cmp     esi, [rdi]
0x18001ed7a  jb      short loc_18001ED05
0x18001ed7c  mov     rcx, rdi
0x18001ed7f  mov     rax, r15
0x18001ed82  call    cs:__guard_dispatch_icall_fptr
0x18001ed88  mov     esi, [rbp+57h+var_C0]
0x18001ed8b  mov     rcx, [r13+8]
0x18001ed8f  test    rcx, rcx
0x18001ed92  jz      short loc_18001EDAE
0x18001ed94  mov     rax, [rcx]
0x18001ed97  mov     r9d, esi
0x18001ed9a  mov     r8d, r12d
0x18001ed9d  mov     rdx, rbx
0x18001eda0  mov     rax, [rax+60h]
0x18001eda4  call    cs:__guard_dispatch_icall_fptr
0x18001edaa  mov     edi, eax
0x18001edac  jmp     short loc_18001EDB3
0x18001edae  mov     edi, 1
0x18001edb3  test    r14, r14
0x18001edb6  jz      short loc_18001EDC1
0x18001edb8  mov     rcx, r14; hLibModule
0x18001edbb  call    cs:__imp_FreeLibrary
0x18001edc1  mov     eax, edi
0x18001edc3  mov     rcx, [rbp+57h+var_50]
0x18001edc7  xor     rcx, rsp; StackCookie
0x18001edca  call    __security_check_cookie
0x18001edcf  add     rsp, 0B8h
0x18001edd6  pop     r15
0x18001edd8  pop     r14
0x18001edda  pop     r13
0x18001eddc  pop     r12
0x18001edde  pop     rdi
0x18001eddf  pop     rsi
0x18001ede0  pop     rbx
0x18001ede1  pop     rbp
0x18001ede2  retn
```
