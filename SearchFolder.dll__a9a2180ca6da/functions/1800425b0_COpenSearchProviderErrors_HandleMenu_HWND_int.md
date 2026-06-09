# COpenSearchProviderErrors::HandleMenu(HWND__ *,int)

- ea: `0x1800425b0`
- end: `0x180042604`
- name: `?HandleMenu@COpenSearchProviderErrors@@UEAAJPEAUHWND__@@H@Z`
- size: `84`
- prototype: `__int64 __fastcall(COpenSearchProviderErrors *__hidden this, HWND, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800425b0`

## import_xrefs

- `ext-ms-win-net-nfdapi-l1-1-0!NdfExecuteDiagnosis` at `0x1800425eb`
- `ext-ms-win-net-nfdapi-l1-1-0!NdfExecuteDiagnosis` at `0x1800425eb`
- `ext-ms-win-net-nfdapi-l1-1-0!NdfCreateWebIncident` at `0x1800425d8`
- `ext-ms-win-net-nfdapi-l1-1-0!NdfCreateWebIncident` at `0x1800425d8`
- `ext-ms-win-net-nfdapi-l1-1-0!NdfCloseIncident` at `0x1800425f6`
- `ext-ms-win-net-nfdapi-l1-1-0!NdfCloseIncident` at `0x1800425f6`

## pseudocode

```c
__int64 __fastcall COpenSearchProviderErrors::HandleMenu(COpenSearchProviderErrors *this, HWND a2, int a3)
{
  HRESULT v3; // ebx
  const WCHAR *v4; // rcx
  NDFHANDLE handle; // [rsp+48h] [rbp+20h] BYREF

  v3 = -2147467259;
  if ( a3 == 1 )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      handle = 0;
      v3 = NdfCreateWebIncident(v4, &handle);
      if ( v3 >= 0 )
      {
        NdfExecuteDiagnosis(handle, 0);
        NdfCloseIncident(handle);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800425b0  push    rbx
0x1800425b2  sub     rsp, 20h
0x1800425b6  mov     ebx, 80004005h
0x1800425bb  cmp     r8d, 1
0x1800425bf  jnz     short loc_1800425FC
0x1800425c1  mov     rcx, [rcx+10h]; url
0x1800425c5  test    rcx, rcx
0x1800425c8  jz      short loc_1800425FC
0x1800425ca  lea     rdx, [rsp+28h+handle]; handle
0x1800425cf  mov     [rsp+28h+handle], 0
0x1800425d8  call    cs:__imp_NdfCreateWebIncident
0x1800425de  mov     ebx, eax
0x1800425e0  test    eax, eax
0x1800425e2  js      short loc_1800425FC
0x1800425e4  mov     rcx, [rsp+28h+handle]; handle
0x1800425e9  xor     edx, edx; hwnd
0x1800425eb  call    cs:__imp_NdfExecuteDiagnosis
0x1800425f1  mov     rcx, [rsp+28h+handle]; handle
0x1800425f6  call    cs:__imp_NdfCloseIncident
0x1800425fc  mov     eax, ebx
0x1800425fe  add     rsp, 20h
0x180042602  pop     rbx
0x180042603  retn
```
