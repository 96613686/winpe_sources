# CRegistry::Close(void)

- ea: `0x140012040`
- end: `0x14001209f`
- name: `?Close@CRegistry@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011cc0`
- `0x140012f60`
- `0x1400134b0`
- `0x1400162be`

## callees

- `0x140012040`
- `0x140013b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012085`

## pseudocode

```c
void __fastcall CRegistry::Close(CRegistry *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    RegCloseKey(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    RegCloseKey(v3);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this && *((_BYTE *)this + 36) )
  {
    RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = 0;
  }
  CRegistry::SetDefaultValues(this);
}

```

## disassembly

```asm
0x140012040  push    rbx
0x140012042  sub     rsp, 20h
0x140012046  mov     rbx, rcx
0x140012049  mov     rcx, [rcx+10h]; hKey
0x14001204d  test    rcx, rcx
0x140012050  jz      short loc_140012060
0x140012052  call    cs:__imp_RegCloseKey
0x140012058  mov     qword ptr [rbx+10h], 0
0x140012060  mov     rcx, [rbx+8]; hKey
0x140012064  test    rcx, rcx
0x140012067  jz      short loc_140012077
0x140012069  call    cs:__imp_RegCloseKey
0x14001206f  mov     qword ptr [rbx+8], 0
0x140012077  mov     rcx, [rbx]; hKey
0x14001207a  test    rcx, rcx
0x14001207d  jz      short loc_140012092
0x14001207f  cmp     byte ptr [rbx+24h], 0
0x140012083  jz      short loc_140012092
0x140012085  call    cs:__imp_RegCloseKey
0x14001208b  mov     qword ptr [rbx], 0
0x140012092  mov     rcx, rbx; this
0x140012095  add     rsp, 20h
0x140012099  pop     rbx
0x14001209a  jmp     ?SetDefaultValues@CRegistry@@AEAAXXZ; CRegistry::SetDefaultValues(void)
```
