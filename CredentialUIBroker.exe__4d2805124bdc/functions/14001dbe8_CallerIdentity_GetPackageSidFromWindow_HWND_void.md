# CallerIdentity::GetPackageSidFromWindow(HWND__ *,void * *)

- ea: `0x14001dbe8`
- end: `0x14001dc2a`
- name: `?GetPackageSidFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAX@Z`
- size: `66`
- prototype: `__int64 __fastcall(CallerIdentity *this, _QWORD *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140018cf8`
- `0x14001d8dc`

## callees

- `0x140013600`
- `0x14001dbe8`
- `0x14001dcfc`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x14001dc05`
- `USER32!GetWindowThreadProcessId` at `0x14001dc05`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromWindow(CallerIdentity *this, _QWORD *a2, void **a3)
{
  void **v4; // r8
  __int64 result; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  dwProcessId = 0;
  if ( GetWindowThreadProcessId((HWND)this, &dwProcessId) )
    return CallerIdentity::GetPackageSidFromProcess(dwProcessId, a2, v4);
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return CallerIdentity::GetPackageSidFromProcess(dwProcessId, a2, v4);
  return result;
}

```

## disassembly

```asm
0x14001dbe8  push    rbx
0x14001dbea  sub     rsp, 20h
0x14001dbee  mov     rbx, rdx
0x14001dbf1  mov     qword ptr [rdx], 0
0x14001dbf8  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x14001dbfd  mov     [rsp+28h+dwProcessId], 0
0x14001dc05  call    cs:__imp_GetWindowThreadProcessId
0x14001dc0b  test    eax, eax
0x14001dc0d  jnz     short loc_14001DC18
0x14001dc0f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001dc14  test    eax, eax
0x14001dc16  js      short loc_14001DC24
0x14001dc18  mov     ecx, [rsp+28h+dwProcessId]; dwProcessId
0x14001dc1c  mov     rdx, rbx; void *
0x14001dc1f  call    ?GetPackageSidFromProcess@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcess(ulong,void * *)
0x14001dc24  add     rsp, 20h
0x14001dc28  pop     rbx
0x14001dc29  retn
```
