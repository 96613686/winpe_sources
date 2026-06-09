# WaitWorker(CRegistryWatcher *,_TP_WAIT *)

- ea: `0x180154a74`
- end: `0x180154b2a`
- name: `?WaitWorker@@YAXPEAVCRegistryWatcher@@PEAU_TP_WAIT@@@Z`
- size: `182`
- prototype: `void(struct CRegistryWatcher *, struct _TP_WAIT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18015497c`
- `0x180154a50`

## callees

- `0x180154a74`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180154a88`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180154a88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180154a98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180154a98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180154af9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180154af9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180154ab7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180154ab7`

## pseudocode

```c
void __fastcall WaitWorker(struct CRegistryWatcher *a1, struct _TP_WAIT *a2)
{
  char v4; // bl
  HKEY v5; // rcx
  __int64 v6; // rcx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  ResetEvent(*((HANDLE *)a1 + 4));
  SetThreadpoolWait(a2, *((HANDLE *)a1 + 4), 0);
  v4 = 1;
  RegNotifyChangeKeyValue(*((HKEY *)a1 + 3), 1, 0x10000004u, *((HANDLE *)a1 + 4), 1);
  v5 = (HKEY)*((_QWORD *)a1 + 3);
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExA(v5, (LPCSTR)a1 + 40, 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    v4 = 0;
  LOBYTE(v6) = v4;
  (*((void (__fastcall **)(__int64, _QWORD, _QWORD))a1 + 1))(v6, Data, *((_QWORD *)a1 + 2));
}

```

## disassembly

```asm
0x180154a74  mov     [rsp+arg_8], rbx
0x180154a79  push    rdi
0x180154a7a  sub     rsp, 30h
0x180154a7e  mov     rdi, rcx
0x180154a81  mov     rbx, rdx
0x180154a84  mov     rcx, [rcx+20h]; hEvent
0x180154a88  call    cs:__imp_ResetEvent
0x180154a8e  mov     rdx, [rdi+20h]; h
0x180154a92  xor     r8d, r8d; pftTimeout
0x180154a95  mov     rcx, rbx; pwa
0x180154a98  call    cs:__imp_SetThreadpoolWait
0x180154a9e  mov     r9, [rdi+20h]; hEvent
0x180154aa2  mov     ebx, 1
0x180154aa7  mov     rcx, [rdi+18h]; hKey
0x180154aab  mov     edx, ebx; bWatchSubtree
0x180154aad  mov     r8d, 10000004h; dwNotifyFilter
0x180154ab3  mov     [rsp+38h+fAsynchronous], ebx; fAsynchronous
0x180154ab7  call    cs:__imp_RegNotifyChangeKeyValue
0x180154abd  mov     rcx, [rdi+18h]; hKey
0x180154ac1  lea     rax, [rsp+38h+cbData]
0x180154ac6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180154acb  lea     rdx, [rdi+28h]; lpValueName
0x180154acf  lea     rax, [rsp+38h+Data]
0x180154ad4  mov     [rsp+38h+Type], 0
0x180154adc  lea     r9, [rsp+38h+Type]; lpType
0x180154ae1  mov     qword ptr [rsp+38h+fAsynchronous], rax; lpData
0x180154ae6  xor     r8d, r8d; lpReserved
0x180154ae9  mov     [rsp+38h+Data], 0
0x180154af1  mov     [rsp+38h+cbData], 4
0x180154af9  call    cs:__imp_RegQueryValueExA
0x180154aff  test    eax, eax
0x180154b01  jnz     short loc_180154B0A
0x180154b03  cmp     [rsp+38h+Type], 4
0x180154b08  jz      short loc_180154B0C
0x180154b0a  xor     bl, bl
0x180154b0c  mov     r8, [rdi+10h]
0x180154b10  mov     cl, bl
0x180154b12  mov     edx, [rsp+38h+Data]
0x180154b16  mov     rax, [rdi+8]
0x180154b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b1f  mov     rbx, [rsp+38h+arg_8]
0x180154b24  add     rsp, 30h
0x180154b28  pop     rdi
0x180154b29  retn
```
