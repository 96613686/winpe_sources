# CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge(ISyncKnowledge * *)

- ea: `0x1800642dc`
- end: `0x1800643ad`
- name: `?GetEmptyChangeBatchKnowledge@CSyncChangeBatchWrapper@@QEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *__hidden this, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800383f4`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800642dc`
- `0x180094010`

## string_xrefs

- `0x18006430e`: `CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge`
- `0x180064386`: `CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge(
        CSyncChangeBatchWrapper *this,
        struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 8);
    v5 = -2147217380;
    if ( v6 )
    {
      v7 = *(_QWORD *)(v6 + 8);
      if ( v7 )
      {
        v5 = 0;
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 8LL))(*(_QWORD *)(v6 + 8));
        *a2 = *(struct ISyncKnowledge **)(*((_QWORD *)this + 8) + 8LL);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      34,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::GetEmptyChangeBatchKnowledge",
      v5);
  return v5;
}

```

## disassembly

```asm
0x1800642dc  push    rbx
0x1800642de  push    rbp
0x1800642df  push    rsi
0x1800642e0  push    rdi
0x1800642e1  sub     rsp, 38h
0x1800642e5  mov     rdi, rdx
0x1800642e8  mov     rsi, rcx
0x1800642eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800642f2  lea     rbp, WPP_GLOBAL_Control
0x1800642f9  cmp     rcx, rbp
0x1800642fc  jz      short loc_18006432D
0x1800642fe  test    byte ptr [rcx+1Ch], 8
0x180064302  jz      short loc_18006432D
0x180064304  cmp     byte ptr [rcx+19h], 5
0x180064308  jb      short loc_18006432D
0x18006430a  mov     rcx, [rcx+10h]
0x18006430e  lea     r9, aCsyncchangebat_46; "CSyncChangeBatchWrapper::GetEmptyChange"...
0x180064315  mov     edx, 21h ; '!'
0x18006431a  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064321  call    WPP_SF_s
0x180064326  mov     rcx, cs:WPP_GLOBAL_Control
0x18006432d  mov     ebx, 80004003h
0x180064332  test    rdi, rdi
0x180064335  jz      short loc_180064371
0x180064337  mov     rax, [rsi+40h]
0x18006433b  mov     ebx, 8004101Ch
0x180064340  test    rax, rax
0x180064343  jz      short loc_180064371
0x180064345  mov     rdx, [rax+8]
0x180064349  test    rdx, rdx
0x18006434c  jz      short loc_180064371
0x18006434e  mov     rax, [rdx]
0x180064351  xor     ebx, ebx
0x180064353  mov     rcx, rdx
0x180064356  mov     rax, [rax+8]
0x18006435a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006435f  mov     rax, [rsi+40h]
0x180064363  mov     rcx, [rax+8]
0x180064367  mov     [rdi], rcx
0x18006436a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064371  cmp     rcx, rbp
0x180064374  jz      short loc_1800643A2
0x180064376  test    byte ptr [rcx+1Ch], 8
0x18006437a  jz      short loc_1800643A2
0x18006437c  cmp     byte ptr [rcx+19h], 5
0x180064380  jb      short loc_1800643A2
0x180064382  mov     rcx, [rcx+10h]
0x180064386  lea     r9, aCsyncchangebat_46; "CSyncChangeBatchWrapper::GetEmptyChange"...
0x18006438d  mov     edx, 22h ; '"'
0x180064392  mov     [rsp+58h+var_38], ebx
0x180064396  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x18006439d  call    WPP_SF_sD
0x1800643a2  mov     eax, ebx
0x1800643a4  add     rsp, 38h
0x1800643a8  pop     rdi
0x1800643a9  pop     rsi
0x1800643aa  pop     rbp
0x1800643ab  pop     rbx
0x1800643ac  retn
```
