# CEmfPlusEnumState::ExcludeClipRect(void)

- ea: `0x180125900`
- end: `0x1801259c9`
- name: `?ExcludeClipRect@CEmfPlusEnumState@@QEAAXXZ`
- size: `201`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011a00`

## callees

- `0x180013270`
- `0x1800fe680`
- `0x180125900`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `GDI32!CombineRgn` at `0x1801259a2`
- `GDI32!CombineRgn` at `0x1801259a2`
- `GDI32!DeleteObject` at `0x1801259ab`
- `GDI32!DeleteObject` at `0x1801259ab`
- `GDI32!CreateRectRgn` at `0x180125972`
- `GDI32!CreateRectRgn` at `0x180125981`
- `GDI32!CreateRectRgn` at `0x180125972`
- `GDI32!CreateRectRgn` at `0x180125981`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::ExcludeClipRect(HRGN *this)
{
  const struct tagENHMETARECORD *PartialRecord; // rax
  __int64 *v3; // rcx
  __int64 v4; // rdx
  const struct tagENHMETARECORD *v5; // rbx
  size_t v6; // r8
  int v7; // ecx
  int iType; // edx
  int nSize; // r8d
  int v10; // r9d
  HRGN RectRgn; // rax
  HRGN v12; // rbx
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h]

  PartialRecord = CEmfPlusEnumState::GetPartialRecord((CEmfPlusEnumState *)this);
  v4 = *v3;
  v5 = PartialRecord;
  v14 = 0;
  v13 = 0;
  v6 = (*(unsigned int (__fastcall **)(__int64 *))(v4 + 48))(v3);
  if ( v6 < 0x18 )
  {
    memcpy_0(&v13, v5, v6);
    v5 = (const struct tagENHMETARECORD *)&v13;
  }
  v7 = v5->dParm[0];
  iType = v5[1].iType;
  nSize = v5[1].nSize;
  v10 = v5[1].dParm[0];
  if ( this[536] )
  {
    RectRgn = CreateRectRgn(v7, iType, nSize, v10);
    v12 = RectRgn;
    if ( RectRgn )
    {
      CombineRgn(this[536], this[536], RectRgn, 2);
      DeleteObject(v12);
    }
  }
  else
  {
    this[536] = CreateRectRgn(v7, iType, nSize, v10);
  }
}

```

## disassembly

```asm
0x180125900  mov     [rsp+arg_8], rbx
0x180125905  push    rdi
0x180125906  sub     rsp, 40h
0x18012590a  mov     rax, cs:__security_cookie
0x180125911  xor     rax, rsp
0x180125914  mov     [rsp+48h+var_10], rax
0x180125919  mov     rdi, rcx
0x18012591c  call    ?GetPartialRecord@CEmfPlusEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; CEmfPlusEnumState::GetPartialRecord(void)
0x180125921  mov     rdx, [rcx]
0x180125924  mov     rbx, rax
0x180125927  xor     eax, eax
0x180125929  xorps   xmm0, xmm0
0x18012592c  mov     [rsp+48h+var_18], rax
0x180125931  movups  [rsp+48h+var_28], xmm0
0x180125936  mov     rax, [rdx+30h]
0x18012593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012593f  mov     r8d, eax; Size
0x180125942  cmp     r8, 18h
0x180125946  jnb     short loc_18012595A
0x180125948  mov     rdx, rbx; Src
0x18012594b  lea     rcx, [rsp+48h+var_28]; void *
0x180125950  call    memcpy_0
0x180125955  lea     rbx, [rsp+48h+var_28]
0x18012595a  cmp     qword ptr [rdi+10C0h], 0
0x180125962  mov     ecx, [rbx+8]; x1
0x180125965  mov     edx, [rbx+0Ch]; y1
0x180125968  mov     r8d, [rbx+10h]; x2
0x18012596c  mov     r9d, [rbx+14h]; y2
0x180125970  jnz     short loc_180125981
0x180125972  call    cs:__imp_CreateRectRgn
0x180125978  mov     [rdi+10C0h], rax
0x18012597f  jmp     short loc_1801259B1
0x180125981  call    cs:__imp_CreateRectRgn
0x180125987  mov     rbx, rax
0x18012598a  test    rax, rax
0x18012598d  jz      short loc_1801259B1
0x18012598f  mov     rcx, [rdi+10C0h]; hrgnDst
0x180125996  mov     r9d, 2; iMode
0x18012599c  mov     rdx, rcx; hrgnSrc1
0x18012599f  mov     r8, rax; hrgnSrc2
0x1801259a2  call    cs:__imp_CombineRgn
0x1801259a8  mov     rcx, rbx; ho
0x1801259ab  call    cs:__imp_DeleteObject
0x1801259b1  mov     rcx, [rsp+48h+var_10]
0x1801259b6  xor     rcx, rsp; StackCookie
0x1801259b9  call    __security_check_cookie
0x1801259be  mov     rbx, [rsp+48h+arg_8]
0x1801259c3  add     rsp, 40h
0x1801259c7  pop     rdi
0x1801259c8  retn
```
