# ClearAppUpdateInfo(APPUPDATEINFO *)

- ea: `0x180044ca0`
- end: `0x180044cf3`
- name: `?ClearAppUpdateInfo@@YAXPEAUAPPUPDATEINFO@@@Z`
- size: `83`
- prototype: `void __fastcall(struct APPUPDATEINFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800153d0`
- `0x1800198bc`

## callees

- `0x180044ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ce7`

## pseudocode

```c
void __fastcall ClearAppUpdateInfo(LPVOID *a1)
{
  if ( a1 )
  {
    if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
      CoTaskMemFree(a1[1]);
    if ( (*((_BYTE *)a1 + 4) & 2) != 0 )
      CoTaskMemFree(a1[2]);
    if ( (*((_BYTE *)a1 + 4) & 4) != 0 )
      CoTaskMemFree(a1[3]);
    if ( (*((_BYTE *)a1 + 4) & 8) != 0 )
      CoTaskMemFree(a1[4]);
  }
}

```

## disassembly

```asm
0x180044ca0  test    rcx, rcx
0x180044ca3  jz      short locret_180044CF2
0x180044ca5  push    rbx
0x180044ca6  sub     rsp, 20h
0x180044caa  test    byte ptr [rcx+4], 1
0x180044cae  mov     rbx, rcx
0x180044cb1  jz      short loc_180044CBD
0x180044cb3  mov     rcx, [rcx+8]; pv
0x180044cb7  call    cs:__imp_CoTaskMemFree
0x180044cbd  test    byte ptr [rbx+4], 2
0x180044cc1  jz      short loc_180044CCD
0x180044cc3  mov     rcx, [rbx+10h]; pv
0x180044cc7  call    cs:__imp_CoTaskMemFree
0x180044ccd  test    byte ptr [rbx+4], 4
0x180044cd1  jz      short loc_180044CDD
0x180044cd3  mov     rcx, [rbx+18h]; pv
0x180044cd7  call    cs:__imp_CoTaskMemFree
0x180044cdd  test    byte ptr [rbx+4], 8
0x180044ce1  jz      short loc_180044CED
0x180044ce3  mov     rcx, [rbx+20h]; pv
0x180044ce7  call    cs:__imp_CoTaskMemFree
0x180044ced  add     rsp, 20h
0x180044cf1  pop     rbx
0x180044cf2  retn
```
