# IsEulaAccepted(void)

- ea: `0x18008b9e0`
- end: `0x18008ba68`
- name: `?IsEulaAccepted@@YA_NXZ`
- size: `136`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180087760`
- `0x180087840`
- `0x18008aed0`
- `0x18008b100`

## callees

- `0x18006f614`
- `0x18008b9e0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008ba3b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008ba3b`
- `WINBRAND!GetInstalledEULAPath` at `0x18008ba26`
- `WINBRAND!GetInstalledEULAPath` at `0x18008ba26`
- `WINBRAND!EulaFreeBuffer` at `0x18008ba54`
- `WINBRAND!EulaFreeBuffer` at `0x18008ba54`

## pseudocode

```c
char IsEulaAccepted(void)
{
  char v1; // [rsp+30h] [rbp+8h] BYREF
  int v2; // [rsp+38h] [rbp+10h] BYREF
  __int64 v3; // [rsp+40h] [rbp+18h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp+20h] BYREF

  v2 = 0;
  v1 = 0;
  wil::wnf_query_nothrow<unsigned long>(&WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED, &v1, &v2, &v3);
  if ( v1 && v2 == 1 )
    return 1;
  pszPath = 0;
  if ( (int)GetInstalledEULAPath(&pszPath) >= 0 )
  {
    if ( PathFileExistsW(pszPath) )
      return 1;
    EulaFreeBuffer(pszPath);
  }
  return 0;
}

```

## disassembly

```asm
0x18008b9e0  mov     rax, rsp
0x18008b9e3  sub     rsp, 28h
0x18008b9e7  lea     r9, [rax+18h]
0x18008b9eb  mov     dword ptr [rax+10h], 0
0x18008b9f2  lea     r8, [rax+10h]
0x18008b9f6  mov     byte ptr [rax+8], 0
0x18008b9fa  lea     rdx, [rax+8]
0x18008b9fe  lea     rcx, WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED
0x18008ba05  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18008ba0a  cmp     [rsp+28h+arg_0], 0
0x18008ba0f  jz      short loc_18008BA18
0x18008ba11  cmp     [rsp+28h+arg_8], 1
0x18008ba16  jz      short loc_18008BA4B
0x18008ba18  lea     rcx, [rsp+28h+pszPath]
0x18008ba1d  mov     [rsp+28h+pszPath], 0
0x18008ba26  call    cs:__imp_GetInstalledEULAPath
0x18008ba2d  nop     dword ptr [rax+rax+00h]
0x18008ba32  test    eax, eax
0x18008ba34  js      short loc_18008BA60
0x18008ba36  mov     rcx, [rsp+28h+pszPath]; pszPath
0x18008ba3b  call    cs:__imp_PathFileExistsW
0x18008ba42  nop     dword ptr [rax+rax+00h]
0x18008ba47  test    eax, eax
0x18008ba49  jz      short loc_18008BA4F
0x18008ba4b  mov     al, 1
0x18008ba4d  jmp     short loc_18008BA62
0x18008ba4f  mov     rcx, [rsp+28h+pszPath]
0x18008ba54  call    cs:__imp_EulaFreeBuffer
0x18008ba5b  nop     dword ptr [rax+rax+00h]
0x18008ba60  xor     al, al
0x18008ba62  add     rsp, 28h
0x18008ba66  retn
```
