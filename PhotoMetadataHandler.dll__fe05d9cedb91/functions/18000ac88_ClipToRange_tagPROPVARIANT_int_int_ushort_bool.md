# ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)

- ea: `0x18000ac88`
- end: `0x18000ada0`
- name: `?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z`
- size: `280`
- prototype: `__int64 __usercall@<rax>(PROPVARIANT *pvarDest@<rcx>, int@<edx>, int@<r8d>, unsigned __int16@<r9w>, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a680`
- `0x18001defc`

## callees

- `0x18000ac88`
- `0x18000adb0`
- `0x18001f474`
- `0x18001f584`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ad59`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ad59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad46`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad65`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad87`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad46`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad65`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad87`

## pseudocode

```c
__int64 __fastcall ClipToRange(PROPVARIANT *pvarDest, LONG a2, LONG a3, unsigned __int16 a4, bool *a5)
{
  int v6; // r13d
  char v9; // si
  HRESULT v10; // ebx
  bool v11; // di
  int v12; // eax
  PROPVARIANT pvar; // [rsp+20h] [rbp-38h] BYREF
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-20h] BYREF

  v6 = a4;
  memset(&pvar, 0, sizeof(pvar));
  v9 = 0;
  v10 = ConvertPropvarToLONG(pvarDest, &pvar);
  v11 = 1;
  if ( v10 >= 0 )
  {
    if ( pvar.lVal >= a2 )
    {
      if ( pvar.lVal <= a3 )
        goto LABEL_17;
      pvar.lVal = a3;
    }
    else
    {
      pvar.lVal = a2;
    }
    v9 = 1;
    memset(&pvarSrc, 0, sizeof(pvarSrc));
    switch ( v6 )
    {
      case 3:
        v12 = ConvertPropvarToLONG(&pvar, &pvarSrc);
        break;
      case 18:
        v12 = ConvertPropvarToUSHORT(&pvar, &pvarSrc);
        break;
      case 19:
        v12 = ConvertPropvarToULONG(&pvar, &pvarSrc);
        break;
      default:
        v10 = -2147316575;
LABEL_16:
        PropVariantClear(&pvarSrc);
        goto LABEL_17;
    }
    v10 = v12;
    if ( v12 >= 0 )
    {
      v10 = PropVariantClear(pvarDest);
      if ( v10 >= 0 )
        v10 = PropVariantCopy(pvarDest, &pvarSrc);
    }
    goto LABEL_16;
  }
LABEL_17:
  if ( a5 )
  {
    if ( v10 < 0 || !v9 )
      v11 = 0;
    *a5 = v11;
  }
  PropVariantClear(&pvar);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ac88  push    rbp
0x18000ac8a  push    rbx
0x18000ac8b  push    rsi
0x18000ac8c  push    rdi
0x18000ac8d  push    r12
0x18000ac8f  push    r13
0x18000ac91  push    r14
0x18000ac93  push    r15
0x18000ac95  mov     rbp, rsp
0x18000ac98  sub     rsp, 58h
0x18000ac9c  mov     r14d, edx
0x18000ac9f  movzx   r13d, r9w
0x18000aca3  xorps   xmm0, xmm0
0x18000aca6  lea     rdx, [rbp+pvar]; pvarDest
0x18000acaa  xor     eax, eax
0x18000acac  mov     r15d, r8d
0x18000acaf  movups  xmmword ptr [rbp+pvar], xmm0
0x18000acb3  mov     qword ptr [rbp+pvar+10h], rax
0x18000acb7  mov     r12, rcx
0x18000acba  xor     sil, sil
0x18000acbd  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000acc2  mov     ebx, eax
0x18000acc4  mov     dil, 1
0x18000acc7  test    eax, eax
0x18000acc9  js      loc_18000AD6B
0x18000accf  cmp     dword ptr [rbp+pvar+8], r14d
0x18000acd3  jge     short loc_18000ACDB
0x18000acd5  mov     dword ptr [rbp+pvar+8], r14d
0x18000acd9  jmp     short loc_18000ACE9
0x18000acdb  cmp     dword ptr [rbp+pvar+8], r15d
0x18000acdf  jle     loc_18000AD6B
0x18000ace5  mov     dword ptr [rbp+pvar+8], r15d
0x18000ace9  xor     eax, eax
0x18000aceb  mov     ecx, r13d
0x18000acee  mov     qword ptr [rbp+pvarSrc+10h], rax
0x18000acf2  xorps   xmm0, xmm0
0x18000acf5  mov     sil, dil
0x18000acf8  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18000acfc  sub     ecx, 3
0x18000acff  jz      short loc_18000AD30
0x18000ad01  sub     ecx, 0Fh
0x18000ad04  jz      short loc_18000AD21
0x18000ad06  cmp     ecx, 1
0x18000ad09  jz      short loc_18000AD12
0x18000ad0b  mov     ebx, 80028CA1h
0x18000ad10  jmp     short loc_18000AD61
0x18000ad12  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000ad16  lea     rcx, [rbp+pvar]; pvarSrc
0x18000ad1a  call    ?ConvertPropvarToULONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToULONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000ad1f  jmp     short loc_18000AD3D
0x18000ad21  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000ad25  lea     rcx, [rbp+pvar]; pvarSrc
0x18000ad29  call    ?ConvertPropvarToUSHORT@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToUSHORT(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000ad2e  jmp     short loc_18000AD3D
0x18000ad30  lea     rdx, [rbp+pvarSrc]; pvarDest
0x18000ad34  lea     rcx, [rbp+pvar]; pvarSrc
0x18000ad38  call    ?ConvertPropvarToLONG@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToLONG(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000ad3d  mov     ebx, eax
0x18000ad3f  test    eax, eax
0x18000ad41  js      short loc_18000AD61
0x18000ad43  mov     rcx, r12; pvar
0x18000ad46  call    cs:__imp_PropVariantClear
0x18000ad4c  mov     ebx, eax
0x18000ad4e  test    eax, eax
0x18000ad50  js      short loc_18000AD61
0x18000ad52  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18000ad56  mov     rcx, r12; pvarDest
0x18000ad59  call    cs:__imp_PropVariantCopy
0x18000ad5f  mov     ebx, eax
0x18000ad61  lea     rcx, [rbp+pvarSrc]; pvar
0x18000ad65  call    cs:__imp_PropVariantClear
0x18000ad6b  mov     rax, [rbp+arg_20]
0x18000ad6f  test    rax, rax
0x18000ad72  jz      short loc_18000AD83
0x18000ad74  test    ebx, ebx
0x18000ad76  js      short loc_18000AD7D
0x18000ad78  test    sil, sil
0x18000ad7b  jnz     short loc_18000AD80
0x18000ad7d  xor     dil, dil
0x18000ad80  mov     [rax], dil
0x18000ad83  lea     rcx, [rbp+pvar]; pvar
0x18000ad87  call    cs:__imp_PropVariantClear
0x18000ad8d  mov     eax, ebx
0x18000ad8f  add     rsp, 58h
0x18000ad93  pop     r15
0x18000ad95  pop     r14
0x18000ad97  pop     r13
0x18000ad99  pop     r12
0x18000ad9b  pop     rdi
0x18000ad9c  pop     rsi
0x18000ad9d  pop     rbx
0x18000ad9e  pop     rbp
0x18000ad9f  retn
```
