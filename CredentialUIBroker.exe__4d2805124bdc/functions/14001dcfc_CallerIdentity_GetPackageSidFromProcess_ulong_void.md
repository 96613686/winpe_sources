# CallerIdentity::GetPackageSidFromProcess(ulong,void * *)

- ea: `0x14001dcfc`
- end: `0x14001dd6a`
- name: `?GetPackageSidFromProcess@CallerIdentity@@YAJKPEAPEAX@Z`
- size: `110`
- prototype: `__int64 __fastcall(DWORD dwProcessId, _QWORD *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001dbe8`

## callees

- `0x140013600`
- `0x14001dcfc`
- `0x14001dd70`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x14001dd1f`
- `KERNEL32!OpenProcess` at `0x14001dd1f`
- `KERNEL32!CloseHandle` at `0x14001dd52`
- `KERNEL32!CloseHandle` at `0x14001dd52`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcess(DWORD dwProcessId, _QWORD *a2, void **a3)
{
  CallerIdentity *v4; // rbx
  void **v5; // r8
  int PackageSidFromProcessHandle; // edi

  *a2 = 0;
  v4 = (CallerIdentity *)OpenProcess(0x1000u, 0, dwProcessId);
  if ( v4 || (PackageSidFromProcessHandle = ResultFromKnownLastError(), PackageSidFromProcessHandle >= 0) )
  {
    PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(v4, a2, v5);
    if ( (unsigned __int64)v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
  }
  return (unsigned int)PackageSidFromProcessHandle;
}

```

## disassembly

```asm
0x14001dcfc  mov     [rsp+arg_0], rbx
0x14001dd01  mov     [rsp+arg_8], rsi
0x14001dd06  push    rdi
0x14001dd07  sub     rsp, 20h
0x14001dd0b  mov     rsi, rdx
0x14001dd0e  mov     qword ptr [rdx], 0
0x14001dd15  mov     r8d, ecx; dwProcessId
0x14001dd18  xor     edx, edx; bInheritHandle
0x14001dd1a  mov     ecx, 1000h; dwDesiredAccess
0x14001dd1f  call    cs:__imp_OpenProcess
0x14001dd25  mov     rbx, rax
0x14001dd28  test    rax, rax
0x14001dd2b  jnz     short loc_14001DD38
0x14001dd2d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001dd32  mov     edi, eax
0x14001dd34  test    eax, eax
0x14001dd36  js      short loc_14001DD58
0x14001dd38  mov     rdx, rsi; void *
0x14001dd3b  mov     rcx, rbx; this
0x14001dd3e  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x14001dd43  mov     edi, eax
0x14001dd45  lea     rax, [rbx-1]
0x14001dd49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001dd4d  ja      short loc_14001DD58
0x14001dd4f  mov     rcx, rbx; hObject
0x14001dd52  call    cs:__imp_CloseHandle
0x14001dd58  mov     rbx, [rsp+28h+arg_0]
0x14001dd5d  mov     eax, edi
0x14001dd5f  mov     rsi, [rsp+28h+arg_8]
0x14001dd64  add     rsp, 20h
0x14001dd68  pop     rdi
0x14001dd69  retn
```
