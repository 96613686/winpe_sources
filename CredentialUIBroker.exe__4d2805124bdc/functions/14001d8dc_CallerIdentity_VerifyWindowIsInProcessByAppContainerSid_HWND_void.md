# CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(HWND__ *,void *)

- ea: `0x14001d8dc`
- end: `0x14001d95f`
- name: `?VerifyWindowIsInProcessByAppContainerSid@CallerIdentity@@YAJPEAUHWND__@@PEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001d730`

## callees

- `0x14001d714`
- `0x14001d8dc`
- `0x14001dbe8`
- `0x14001dd70`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x14001d92e`
- `ntdll!RtlEqualSid` at `0x14001d92e`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(
        CallerIdentity *this,
        CallerIdentity *a2,
        void **a3)
{
  int PackageSidFromProcessHandle; // ebx
  void **v5; // r8
  PSID Sid2; // [rsp+40h] [rbp+18h] BYREF
  PSID Sid1; // [rsp+48h] [rbp+20h] BYREF

  Sid1 = 0;
  PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(a2, &Sid1, a3);
  if ( PackageSidFromProcessHandle >= 0 )
  {
    Sid2 = 0;
    PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromWindow(this, &Sid2, v5);
    if ( PackageSidFromProcessHandle >= 0 && !RtlEqualSid(Sid1, Sid2) )
      PackageSidFromProcessHandle = -2147024891;
    CLocalMemPtr<void>::~CLocalMemPtr<void>(&Sid2);
  }
  CLocalMemPtr<void>::~CLocalMemPtr<void>(&Sid1);
  return (unsigned int)PackageSidFromProcessHandle;
}

```

## disassembly

```asm
0x14001d8dc  mov     [rsp+arg_0], rbx
0x14001d8e1  push    rdi
0x14001d8e2  sub     rsp, 20h
0x14001d8e6  mov     rax, rdx
0x14001d8e9  mov     [rsp+28h+Sid1], 0
0x14001d8f2  mov     rdi, rcx
0x14001d8f5  lea     rdx, [rsp+28h+Sid1]; void *
0x14001d8fa  mov     rcx, rax; this
0x14001d8fd  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x14001d902  mov     ebx, eax
0x14001d904  test    eax, eax
0x14001d906  js      short loc_14001D948
0x14001d908  lea     rdx, [rsp+28h+Sid2]; HWND
0x14001d90d  mov     [rsp+28h+Sid2], 0
0x14001d916  mov     rcx, rdi; this
0x14001d919  call    ?GetPackageSidFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAX@Z; CallerIdentity::GetPackageSidFromWindow(HWND__ *,void * *)
0x14001d91e  mov     ebx, eax
0x14001d920  test    eax, eax
0x14001d922  js      short loc_14001D93E
0x14001d924  mov     rdx, [rsp+28h+Sid2]; Sid2
0x14001d929  mov     rcx, [rsp+28h+Sid1]; Sid1
0x14001d92e  call    cs:__imp_RtlEqualSid
0x14001d934  test    al, al
0x14001d936  mov     ecx, 80070005h
0x14001d93b  cmovz   ebx, ecx
0x14001d93e  lea     rcx, [rsp+28h+Sid2]
0x14001d943  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x14001d948  lea     rcx, [rsp+28h+Sid1]
0x14001d94d  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x14001d952  mov     eax, ebx
0x14001d954  mov     rbx, [rsp+28h+arg_0]
0x14001d959  add     rsp, 20h
0x14001d95d  pop     rdi
0x14001d95e  retn
```
