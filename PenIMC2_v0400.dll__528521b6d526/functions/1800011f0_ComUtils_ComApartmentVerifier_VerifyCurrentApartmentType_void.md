# ComUtils::ComApartmentVerifier::VerifyCurrentApartmentType(void)

- ea: `0x1800011f0`
- end: `0x180001240`
- name: `?VerifyCurrentApartmentType@ComApartmentVerifier@ComUtils@@QEAAJXZ`
- size: `80`
- prototype: `__int64 __fastcall(ComUtils::ComApartmentVerifier *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001240`
- `0x1800012c0`

## callees

- `0x1800011f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001226`
- `KERNEL32!GetCurrentThreadId` at `0x180001226`
- `ole32!CoGetApartmentType` at `0x180001212`
- `ole32!CoGetApartmentType` at `0x180001212`

## pseudocode

```c
__int64 __fastcall ComUtils::ComApartmentVerifier::VerifyCurrentApartmentType(ComUtils::ComApartmentVerifier *this)
{
  unsigned int v2; // edi
  APTTYPE pAptType; // [rsp+30h] [rbp+8h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+38h] [rbp+10h] BYREF

  v2 = -2147417842;
  if ( *((_BYTE *)this + 12) )
  {
    CoGetApartmentType(&pAptType, &pAptQualifier);
    if ( pAptType == *(_DWORD *)this && (!*((_BYTE *)this + 4) || *((_DWORD *)this + 2) == GetCurrentThreadId()) )
      return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800011f0  mov     [rsp+arg_10], rbx
0x1800011f5  push    rdi
0x1800011f6  sub     rsp, 20h
0x1800011fa  cmp     byte ptr [rcx+0Ch], 0
0x1800011fe  mov     rbx, rcx
0x180001201  mov     edi, 8001010Eh
0x180001206  jz      short loc_180001233
0x180001208  lea     rdx, [rsp+28h+pAptQualifier]; pAptQualifier
0x18000120d  lea     rcx, [rsp+28h+pAptType]; pAptType
0x180001212  call    cs:__imp_CoGetApartmentType
0x180001218  mov     eax, [rbx]
0x18000121a  cmp     [rsp+28h+pAptType], eax
0x18000121e  jnz     short loc_180001233
0x180001220  cmp     byte ptr [rbx+4], 0
0x180001224  jz      short loc_180001231
0x180001226  call    cs:__imp_GetCurrentThreadId
0x18000122c  cmp     [rbx+8], eax
0x18000122f  jnz     short loc_180001233
0x180001231  xor     edi, edi
0x180001233  mov     rbx, [rsp+28h+arg_10]
0x180001238  mov     eax, edi
0x18000123a  add     rsp, 20h
0x18000123e  pop     rdi
0x18000123f  retn
```
