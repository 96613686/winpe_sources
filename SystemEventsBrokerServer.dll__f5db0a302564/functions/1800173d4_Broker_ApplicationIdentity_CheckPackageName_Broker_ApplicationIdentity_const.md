# Broker::ApplicationIdentity::CheckPackageName(Broker::ApplicationIdentity const &)

- ea: `0x1800173d4`
- end: `0x180017433`
- name: `?CheckPackageName@ApplicationIdentity@Broker@@QEBA_NAEBU12@@Z`
- size: `95`
- prototype: `bool __fastcall(Broker::ApplicationIdentity *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e880`

## callees

- `0x1800173d4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180017422`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180017422`

## pseudocode

```c
bool __fastcall Broker::ApplicationIdentity::CheckPackageName(
        Broker::ApplicationIdentity *this,
        const struct Broker::ApplicationIdentity *a2)
{
  int cchCount2; // eax
  char *lpString2; // rdx
  const WCHAR *v4; // r8

  cchCount2 = *((_DWORD *)a2 + 10);
  lpString2 = (char *)a2 + 24;
  if ( *((_QWORD *)lpString2 + 3) > 7u )
    lpString2 = *(char **)lpString2;
  v4 = (const WCHAR *)((char *)this + 24);
  if ( *((_QWORD *)this + 6) > 7u )
    v4 = *(const WCHAR **)v4;
  return CompareStringEx(&LocaleName, 1u, v4, *((_DWORD *)this + 10), (LPCWCH)lpString2, cchCount2, 0, 0, 0) == 2;
}

```

## disassembly

```asm
0x1800173d4  sub     rsp, 58h
0x1800173d8  mov     eax, [rdx+28h]
0x1800173db  add     rdx, 18h
0x1800173df  cmp     qword ptr [rdx+18h], 7
0x1800173e4  jbe     short loc_1800173E9
0x1800173e6  mov     rdx, [rdx]
0x1800173e9  lea     r8, [rcx+18h]
0x1800173ed  cmp     qword ptr [r8+18h], 7
0x1800173f2  jbe     short loc_1800173F7
0x1800173f4  mov     r8, [r8]; lpString1
0x1800173f7  xor     r9d, r9d
0x1800173fa  mov     [rsp+58h+lParam], r9; lParam
0x1800173ff  mov     [rsp+58h+lpReserved], r9; lpReserved
0x180017404  mov     [rsp+58h+lpVersionInformation], r9; lpVersionInformation
0x180017409  mov     r9d, [rcx+28h]; cchCount1
0x18001740d  lea     rcx, LocaleName; lpLocaleName
0x180017414  mov     [rsp+58h+cchCount2], eax; cchCount2
0x180017418  mov     [rsp+58h+lpString2], rdx; lpString2
0x18001741d  mov     edx, 1; dwCmpFlags
0x180017422  call    cs:__imp_CompareStringEx
0x180017428  cmp     eax, 2
0x18001742b  setz    al
0x18001742e  add     rsp, 58h
0x180017432  retn
```
