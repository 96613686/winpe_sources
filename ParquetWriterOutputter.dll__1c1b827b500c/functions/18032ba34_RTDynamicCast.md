# __RTDynamicCast

- ea: `0x18032ba34`
- end: `0x18032bb9a`
- name: `__RTDynamicCast`
- size: `358`
- prototype: ``
- caller_count: `83`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011d80`
- `0x180011ee0`
- `0x18002cc90`
- `0x18002ccc0`
- `0x18002ccf0`
- `0x18002d220`
- `0x18002d280`
- `0x18002d310`
- `0x18002d350`
- `0x18002d380`
- `0x180035140`
- `0x1800401e0`
- `0x180040400`
- `0x180040940`
- `0x180040b60`
- `0x180040d80`
- `0x180040fa0`
- `0x180041270`
- `0x180041540`
- `0x180041810`
- `0x180041a30`
- `0x180041d00`
- `0x180041fd0`
- `0x1800421f0`
- `0x180042410`
- `0x1800426e0`
- `0x1800429b0`
- `0x18004a2a0`
- `0x18004a570`
- `0x18004aae0`
- `0x18004aca0`
- `0x18004ae50`
- `0x18004b230`
- `0x18004b470`
- `0x18004b6b0`
- `0x18004b8f0`
- `0x18004bab0`
- `0x18004bcf0`
- `0x18004c040`
- `0x18004c310`
- `0x18004c730`
- `0x18004c970`
- `0x18004cbb0`
- `0x18004e4a0`
- `0x18004e520`
- `0x18004e5a0`
- `0x18004e620`
- `0x18004e6a0`
- `0x18004e720`
- `0x18004e7a0`

## callees

- `0x18032b080`
- `0x18032b508`
- `0x18032b690`
- `0x18032b7cc`
- `0x18032b9ec`
- `0x18032ba04`
- `0x18032ba34`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x18032baab`
- `KERNEL32!RtlPcToFileHeader` at `0x18032baab`

## string_xrefs

- `0x18032bb53`: `Access violation - no RTTI data!`

## pseudocode

```c
char *__fastcall _RTDynamicCast(_QWORD *a1, int a2, __int64 a3, __int64 a4, int a5)
{
  int v8; // edi
  __int64 v9; // rbx
  _DWORD *v11; // rsi
  char *v12; // r14
  char *v13; // r9
  int v14; // ecx
  int *VITargetTypeInstance; // rax
  __int64 v16; // r8
  int v17; // r9d
  __int64 v18; // [rsp+28h] [rbp-50h]
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-48h] BYREF
  PVOID BaseOfImage; // [rsp+80h] [rbp+8h] BYREF

  v8 = (int)a1;
  v9 = 0;
  if ( !a1 )
    return 0;
  v11 = *(_DWORD **)(*a1 - 8LL);
  v12 = (char *)a1 - (unsigned int)v11[1] - (v11[2] != 0 ? *(_DWORD *)((char *)a1 - (unsigned int)v11[2]) : 0);
  if ( *v11 )
  {
    v13 = (char *)v11 - (int)v11[5];
  }
  else
  {
    v13 = (char *)RtlPcToFileHeader(v11, &BaseOfImage);
    BaseOfImage = v13;
  }
  v14 = *(_DWORD *)&v13[v11[4] + 4];
  if ( (v14 & 1) != 0 )
  {
    v18 = (__int64)v13;
    v17 = v8 - a2 - (_DWORD)v12;
    if ( (v14 & 2) != 0 )
      VITargetTypeInstance = (int *)FindVITargetTypeInstance((_DWORD)v12, (_DWORD)v11, a3, v17, a4, v18);
    else
      VITargetTypeInstance = (int *)FindMITargetTypeInstance((_DWORD)v12, (_DWORD)v11, a3, v17, a4, v18);
  }
  else
  {
    VITargetTypeInstance = (int *)FindSITargetTypeInstance(v11, a3, a4);
  }
  if ( VITargetTypeInstance )
  {
    if ( VITargetTypeInstance[3] >= 0 )
      v9 = *(int *)(*(_QWORD *)&v12[VITargetTypeInstance[3]] + VITargetTypeInstance[4])
         + (__int64)VITargetTypeInstance[3];
    return &v12[v9 + VITargetTypeInstance[2]];
  }
  else
  {
    if ( a5 )
    {
      std::bad_cast::__construct_from_string_literal(pExceptionObject, "Bad dynamic_cast!", v16, 0);
      throw (std::bad_cast *)pExceptionObject;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18032ba34  mov     [rsp+arg_8], rbx
0x18032ba39  mov     [rsp+arg_10], rsi
0x18032ba3e  push    rdi
0x18032ba3f  push    r12
0x18032ba41  push    r13
0x18032ba43  push    r14
0x18032ba45  push    r15
0x18032ba47  sub     rsp, 50h
0x18032ba4b  mov     r15, r9
0x18032ba4e  mov     r12, r8
0x18032ba51  movsxd  r13, edx
0x18032ba54  mov     rdi, rcx
0x18032ba57  xor     ebx, ebx
0x18032ba59  test    rcx, rcx
0x18032ba5c  jnz     short loc_18032BA7A
0x18032ba5e  xor     eax, eax
0x18032ba60  lea     r11, [rsp+78h+var_28]
0x18032ba65  mov     rbx, [r11+38h]
0x18032ba69  mov     rsi, [r11+40h]
0x18032ba6d  mov     rsp, r11
0x18032ba70  pop     r15
0x18032ba72  pop     r14
0x18032ba74  pop     r13
0x18032ba76  pop     r12
0x18032ba78  pop     rdi
0x18032ba79  retn
0x18032ba7a  mov     rax, [rcx]
0x18032ba7d  mov     rsi, [rax-8]
0x18032ba81  mov     eax, [rsi+4]
0x18032ba84  mov     r14, rdi
0x18032ba87  sub     r14, rax
0x18032ba8a  mov     edx, [rsi+8]
0x18032ba8d  sub     rcx, rdx
0x18032ba90  neg     edx
0x18032ba92  sbb     eax, eax
0x18032ba94  and     eax, [rcx]
0x18032ba96  movsxd  rcx, eax
0x18032ba99  sub     r14, rcx
0x18032ba9c  cmp     [rsi], ebx
0x18032ba9e  jnz     short loc_18032BABE
0x18032baa0  lea     rdx, [rsp+78h+BaseOfImage]; BaseOfImage
0x18032baa8  mov     rcx, rsi; PcValue
0x18032baab  call    cs:__imp_RtlPcToFileHeader
0x18032bab1  mov     r9, rax
0x18032bab4  mov     [rsp+78h+BaseOfImage], rax
0x18032babc  jmp     short loc_18032BAC8
0x18032babe  movsxd  rax, dword ptr [rsi+14h]
0x18032bac2  mov     r9, rsi
0x18032bac5  sub     r9, rax
0x18032bac8  movsxd  rax, dword ptr [rsi+10h]
0x18032bacc  mov     ecx, [rax+r9+4]
0x18032bad1  test    cl, 1
0x18032bad4  jnz     short loc_18032BAE6
0x18032bad6  mov     r8, r15
0x18032bad9  mov     rdx, r12
0x18032badc  mov     rcx, rsi
0x18032badf  call    FindSITargetTypeInstance
0x18032bae4  jmp     short loc_18032BB13
0x18032bae6  sub     rdi, r13
0x18032bae9  sub     rdi, r14
0x18032baec  mov     [rsp+78h+var_50], r9
0x18032baf1  mov     r8, r12
0x18032baf4  mov     rdx, rsi
0x18032baf7  mov     [rsp+78h+var_58], r15
0x18032bafc  mov     r9, rdi
0x18032baff  test    cl, 2
0x18032bb02  mov     rcx, r14
0x18032bb05  jnz     short loc_18032BB0E
0x18032bb07  call    FindMITargetTypeInstance
0x18032bb0c  jmp     short loc_18032BB13
0x18032bb0e  call    FindVITargetTypeInstance
0x18032bb13  mov     r9, rax
0x18032bb16  test    rax, rax
0x18032bb19  jnz     short loc_18032BB2B
0x18032bb1b  cmp     [rsp+78h+arg_20], ebx
0x18032bb22  jnz     short loc_18032BB76
0x18032bb24  xor     eax, eax
0x18032bb26  jmp     loc_18032BA60
0x18032bb2b  cmp     [r9+0Ch], ebx
0x18032bb2f  jl      short loc_18032BB44
0x18032bb31  movsxd  rbx, dword ptr [r9+0Ch]
0x18032bb35  movsxd  rcx, dword ptr [r9+10h]
0x18032bb39  mov     rax, [rbx+r14]
0x18032bb3d  movsxd  rcx, dword ptr [rax+rcx]
0x18032bb41  add     rbx, rcx
0x18032bb44  movsxd  rax, dword ptr [r9+8]
0x18032bb48  add     rax, rbx
0x18032bb4b  add     rax, r14
0x18032bb4e  jmp     loc_18032BA60
0x18032bb53  lea     rdx, aAccessViolatio
0x18032bb5a  lea     rcx, [rsp+78h+pExceptionObject]
0x18032bb5f  call    ?__construct_from_string_literal@__non_rtti_object@std@@SA?AV12@QEBD@Z
0x18032bb64  lea     rdx, _TI3?AV__non_rtti_object@std@@; pThrowInfo
0x18032bb6b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18032bb70  call    _CxxThrowException
0x18032bb76  lea     rdx, aBadDynamicCast
0x18032bb7d  lea     rcx, [rsp+78h+pExceptionObject]
0x18032bb82  call    ?__construct_from_string_literal@bad_cast@std@@SA?AV12@QEBD@Z
0x18032bb87  lea     rdx, _TI2?AVbad_cast@std@@; pThrowInfo
0x18032bb8e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18032bb93  call    _CxxThrowException
0x18036a967  push    rbp
0x18036a969  sub     rsp, 30h
0x18036a96d  mov     rbp, rdx
0x18036a970  mov     rax, [rcx]
0x18036a973  xor     ecx, ecx
0x18036a975  cmp     dword ptr [rax], 0C0000005h
0x18036a97b  setz    cl
0x18036a97e  mov     eax, ecx
0x18036a980  add     rsp, 30h
0x18036a984  pop     rbp
0x18036a985  retn
```
