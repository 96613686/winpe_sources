# ComUtils::ComApartmentVerifier::CurrentSta(void)

- ea: `0x180001190`
- end: `0x1800011ed`
- name: `?CurrentSta@ComApartmentVerifier@ComUtils@@SA?AV12@XZ`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006ba4`
- `0x180009820`
- `0x18000a444`

## callees

- `0x180001190`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800011bc`
- `KERNEL32!GetCurrentThreadId` at `0x1800011bc`
- `ole32!CoGetApartmentType` at `0x1800011a7`
- `ole32!CoGetApartmentType` at `0x1800011a7`

## pseudocode

```c
__int64 __fastcall ComUtils::ComApartmentVerifier::CurrentSta(__int64 a1)
{
  char v2; // di
  DWORD CurrentThreadId; // eax
  APTTYPE v4; // ecx
  __int64 result; // rax
  APTTYPE pAptType; // [rsp+38h] [rbp+10h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+40h] [rbp+18h] BYREF

  CoGetApartmentType(&pAptType, &pAptQualifier);
  v2 = 0;
  if ( pAptType == APTTYPE_STA || pAptType == APTTYPE_MAINSTA )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = pAptType;
    *(_DWORD *)a1 = pAptType;
    *(_BYTE *)(a1 + 4) = 1;
    *(_DWORD *)(a1 + 8) = CurrentThreadId;
    if ( v4 == APTTYPE_STA || v4 == APTTYPE_MAINSTA )
      v2 = 1;
  }
  result = a1;
  *(_BYTE *)(a1 + 12) = v2;
  return result;
}

```

## disassembly

```asm
0x180001190  mov     [rsp+arg_0], rbx
0x180001195  push    rdi
0x180001196  sub     rsp, 20h
0x18000119a  mov     rbx, rcx
0x18000119d  lea     rdx, [rsp+28h+pAptQualifier]; pAptQualifier
0x1800011a2  lea     rcx, [rsp+28h+pAptType]; pAptType
0x1800011a7  call    cs:__imp_CoGetApartmentType
0x1800011ad  xor     edi, edi
0x1800011af  cmp     [rsp+28h+pAptType], edi
0x1800011b3  jz      short loc_1800011BC
0x1800011b5  cmp     [rsp+28h+pAptType], 3
0x1800011ba  jnz     short loc_1800011DB
0x1800011bc  call    cs:__imp_GetCurrentThreadId
0x1800011c2  mov     ecx, [rsp+28h+pAptType]
0x1800011c6  mov     [rbx], ecx
0x1800011c8  mov     byte ptr [rbx+4], 1
0x1800011cc  mov     [rbx+8], eax
0x1800011cf  test    ecx, ecx
0x1800011d1  jz      short loc_1800011D8
0x1800011d3  cmp     ecx, 3
0x1800011d6  jnz     short loc_1800011DB
0x1800011d8  mov     dil, 1
0x1800011db  mov     rax, rbx
0x1800011de  mov     [rbx+0Ch], dil
0x1800011e2  mov     rbx, [rsp+28h+arg_0]
0x1800011e7  add     rsp, 20h
0x1800011eb  pop     rdi
0x1800011ec  retn
```
