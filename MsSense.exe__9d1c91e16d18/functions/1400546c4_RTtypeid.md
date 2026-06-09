# __RTtypeid

- ea: `0x1400546c4`
- end: `0x140054772`
- name: `__RTtypeid`
- size: `174`
- prototype: `char *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140046eb4`
- `0x140084713`

## callees

- `0x140052f70`
- `0x140054504`
- `0x14005453c`
- `0x1400546c4`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x1400546e3`
- `KERNEL32!RtlPcToFileHeader` at `0x1400546e3`

## string_xrefs

- `0x14005474f`: `Access violation - no RTTI data!`
- `0x140054709`: `Attempted a typeid of nullptr pointer!`
- `0x14005472c`: `Bad read pointer - no RTTI data!`

## pseudocode

```c
char *__fastcall _RTtypeid(_QWORD *a1)
{
  int *v1; // rbx
  char *v2; // rcx
  char *result; // rax
  _BYTE v4[40]; // [rsp+20h] [rbp-28h] BYREF
  PVOID BaseOfImage; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
  {
    sub_14005453C(v4, "Attempted a typeid of nullptr pointer!");
    sub_140052F70(v4, &_TI2_AVbad_typeid_std__);
    goto LABEL_8;
  }
  v1 = *(int **)(*a1 - 8LL);
  if ( *v1 )
  {
    v2 = (char *)v1 - v1[5];
  }
  else
  {
    v2 = (char *)RtlPcToFileHeader(v1, &BaseOfImage);
    BaseOfImage = v2;
  }
  result = &v2[v1[3]];
  if ( !result )
  {
LABEL_8:
    sub_140054504(v4, "Bad read pointer - no RTTI data!");
    sub_140052F70(v4, &_TI3_AV__non_rtti_object_std__);
    sub_140054504(v4, "Access violation - no RTTI data!");
    sub_140052F70(v4, &_TI3_AV__non_rtti_object_std__);
    JUMPOUT(0x140054772LL);
  }
  return result;
}

```

## disassembly

```asm
0x1400546c4  push    rbx
0x1400546c6  sub     rsp, 40h
0x1400546ca  test    rcx, rcx
0x1400546cd  jz      short loc_140054709
0x1400546cf  mov     rax, [rcx]
0x1400546d2  mov     rbx, [rax-8]
0x1400546d6  mov     rcx, rbx; PcValue
0x1400546d9  cmp     dword ptr [rbx], 0
0x1400546dc  jnz     short loc_1400546F3
0x1400546de  lea     rdx, [rsp+48h+BaseOfImage]; BaseOfImage
0x1400546e3  call    cs:RtlPcToFileHeader
0x1400546e9  mov     rcx, rax
0x1400546ec  mov     [rsp+48h+BaseOfImage], rax
0x1400546f1  jmp     short loc_1400546FA
0x1400546f3  movsxd  rax, dword ptr [rbx+14h]
0x1400546f7  sub     rcx, rax
0x1400546fa  movsxd  rax, dword ptr [rbx+0Ch]
0x1400546fe  add     rax, rcx
0x140054701  jz      short loc_14005472C
0x140054703  add     rsp, 40h
0x140054707  pop     rbx
0x140054708  retn
0x140054709  lea     rdx, aAttemptedAType
0x140054710  lea     rcx, [rsp+48h+var_28]
0x140054715  call    sub_14005453C
0x14005471a  lea     rdx, __TI2?AVbad_typeid@std@@; throw info for 'class std::bad_typeid'
0x140054721  lea     rcx, [rsp+48h+var_28]
0x140054726  call    sub_140052F70
0x14005472b  nop
0x14005472c  lea     rdx, aBadReadPointer
0x140054733  lea     rcx, [rsp+48h+var_28]
0x140054738  call    sub_140054504
0x14005473d  lea     rdx, __TI3?AV__non_rtti_object@std@@; throw info for 'class std::__non_rtti_object'
0x140054744  lea     rcx, [rsp+48h+var_28]
0x140054749  call    sub_140052F70
0x14005474e  nop
0x14005474f  lea     rdx, aAccessViolatio
0x140054756  lea     rcx, [rsp+48h+var_28]
0x14005475b  call    sub_140054504
0x140054760  lea     rdx, __TI3?AV__non_rtti_object@std@@; throw info for 'class std::__non_rtti_object'
0x140054767  lea     rcx, [rsp+48h+var_28]
0x14005476c  call    sub_140052F70
0x140054771  nop
0x1400854a0  push    rbp; Microsoft VisualC v14 64bit runtime
0x1400854a2  sub     rsp, 20h
0x1400854a6  mov     rbp, rdx
0x1400854a9  mov     rax, [rcx]
0x1400854ac  xor     ecx, ecx
0x1400854ae  cmp     dword ptr [rax], 0C0000005h
0x1400854b4  setz    cl
0x1400854b7  mov     eax, ecx
0x1400854b9  add     rsp, 20h
0x1400854bd  pop     rbp
0x1400854be  retn
```
