# imp_ApxObjectDelete

- ea: `0x18000d210`
- end: `0x18000d2db`
- name: `imp_ApxObjectDelete`
- size: `203`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *)`
- caller_count: `14`
- callee_count: `6`
- tags: ``

## callers

- `0x1800108e8`
- `0x180016db0`
- `0x180017ba4`
- `0x1800181ac`
- `0x180019c10`
- `0x18001b830`
- `0x18001c400`
- `0x18001d680`
- `0x18001f1d0`
- `0x1800208ec`
- `0x1800246d0`
- `0x180025310`
- `0x180025b00`
- `0x180026e40`

## callees

- `0x18000a12c`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000d168`
- `0x18000d210`
- `0x18002a010`

## pseudocode

```c
void __fastcall imp_ApxObjectDelete(Apx::ApfVerify *this, Apx::ApfVerify *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // r8
  unsigned __int64 v6; // rbx
  void *v7; // rdx
  int v8; // r8d
  char *v9; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d6da6cbbd71936614225fb21bd163213_Traceguids);
  }
  if ( (int)Apx::ApfVerify::IsNull(this, L"Globals", a3) >= 0 && (int)Apx::ApfVerify::IsNotNull(a2, L"Object", v5) >= 0 )
  {
    v6 = ~(unsigned __int64)a2;
    if ( v6 )
    {
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 8LL))(v6);
      Apx::ApfObject::ApfObjectDereferenceActual((Apx::ApfObject *)v6, v7, v8, v9);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d6da6cbbd71936614225fb21bd163213_Traceguids);
  }
}

```

## disassembly

```asm
0x18000d210  mov     [rsp+arg_0], rbx
0x18000d215  mov     [rsp+arg_8], rsi
0x18000d21a  push    rdi
0x18000d21b  sub     rsp, 20h
0x18000d21f  mov     rbx, rdx
0x18000d222  mov     rdi, rcx
0x18000d225  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d22c  lea     rsi, WPP_GLOBAL_Control
0x18000d233  cmp     rcx, rsi
0x18000d236  jz      short loc_18000D259
0x18000d238  test    byte ptr [rcx+1Ch], 1
0x18000d23c  jz      short loc_18000D259
0x18000d23e  cmp     byte ptr [rcx+19h], 5
0x18000d242  jb      short loc_18000D259
0x18000d244  mov     rcx, [rcx+10h]
0x18000d248  lea     r8, WPP_d6da6cbbd71936614225fb21bd163213_Traceguids
0x18000d24f  mov     edx, 0Eh
0x18000d254  call    WPP_SF_
0x18000d259  lea     rdx, aGlobals; "Globals"
0x18000d260  mov     rcx, rdi; this
0x18000d263  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18000d268  test    eax, eax
0x18000d26a  js      short loc_18000D29E
0x18000d26c  lea     rdx, aObject; "Object"
0x18000d273  mov     rcx, rbx; this
0x18000d276  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18000d27b  test    eax, eax
0x18000d27d  js      short loc_18000D29E
0x18000d27f  not     rbx
0x18000d282  test    rbx, rbx
0x18000d285  jz      short loc_18000D29E
0x18000d287  mov     rax, [rbx]
0x18000d28a  mov     rcx, rbx
0x18000d28d  mov     rax, [rax+8]
0x18000d291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d296  mov     rcx, rbx; this
0x18000d299  call    ?ApfObjectDereferenceActual@ApfObject@Apx@@QEAAXPEAXJPEAD@Z; Apx::ApfObject::ApfObjectDereferenceActual(void *,long,char *)
0x18000d29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a5  cmp     rcx, rsi
0x18000d2a8  jz      short loc_18000D2CB
0x18000d2aa  test    byte ptr [rcx+1Ch], 1
0x18000d2ae  jz      short loc_18000D2CB
0x18000d2b0  cmp     byte ptr [rcx+19h], 5
0x18000d2b4  jb      short loc_18000D2CB
0x18000d2b6  mov     rcx, [rcx+10h]
0x18000d2ba  lea     r8, WPP_d6da6cbbd71936614225fb21bd163213_Traceguids
0x18000d2c1  mov     edx, 0Fh
0x18000d2c6  call    WPP_SF_
0x18000d2cb  mov     rbx, [rsp+28h+arg_0]
0x18000d2d0  mov     rsi, [rsp+28h+arg_8]
0x18000d2d5  add     rsp, 20h
0x18000d2d9  pop     rdi
0x18000d2da  retn
```
