# std::unique_ptr<HKEY__ *,AppMon::RegKeyCloser>::~unique_ptr<HKEY__ *,AppMon::RegKeyCloser>(void)

- ea: `0x18000b3a8`
- end: `0x18000b3c2`
- name: `??1?$unique_ptr@PEAUHKEY__@@URegKeyCloser@AppMon@@@std@@QEAA@XZ`
- size: `26`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b558`
- `0x18000bafc`
- `0x18000c234`
- `0x18000f91e`
- `0x18000f978`
- `0x18000f9f6`
- `0x18000fa74`
- `0x18000fa98`

## callees

- `0x18000b3a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3b7`

## pseudocode

```c
LSTATUS __fastcall std::unique_ptr<HKEY__ *,AppMon::RegKeyCloser>::~unique_ptr<HKEY__ *,AppMon::RegKeyCloser>(
        HKEY **a1)
{
  HKEY *v1; // rcx
  LSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RegCloseKey(*v1);
  return result;
}

```

## disassembly

```asm
0x18000b3a8  sub     rsp, 28h
0x18000b3ac  mov     rcx, [rcx]
0x18000b3af  test    rcx, rcx
0x18000b3b2  jz      short loc_18000B3BD
0x18000b3b4  mov     rcx, [rcx]; hKey
0x18000b3b7  call    cs:__imp_RegCloseKey
0x18000b3bd  add     rsp, 28h
0x18000b3c1  retn
```
