# imp_ApxCircuitFactoryRemoveCircuit

- ea: `0x180012340`
- end: `0x180012451`
- name: `imp_ApxCircuitFactoryRemoveCircuit`
- size: `273`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a12c`
- `0x18000a8e8`
- `0x18000a948`
- `0x180011ab8`
- `0x180011e6c`
- `0x180012340`

## pseudocode

```c
__int64 __fastcall imp_ApxCircuitFactoryRemoveCircuit(Apx::ApfVerify *this, Apx::ApfVerify *a2, Apx::ApfVerify *a3)
{
  int IsNull; // ebx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r8
  int v9; // eax
  _QWORD *v10; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids);
  }
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_14;
  IsNull = Apx::ApfVerify::IsNotNull(a2, L"Factory", v7);
  if ( IsNull < 0 )
    goto LABEL_14;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Circuit", v8);
  if ( IsNull < 0 )
    goto LABEL_14;
  v9 = Apx::ApfCircuitFactory::RemoveCircuit(~(unsigned __int64)a2, ~(unsigned __int64)a3);
  IsNull = v9;
  if ( v9 >= 0 )
  {
    IsNull = 0;
    goto LABEL_14;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids, a2, a3, v9);
LABEL_14:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_(v10[2], 20, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x180012340  push    rbx
0x180012342  push    rbp
0x180012343  push    rsi
0x180012344  push    rdi
0x180012345  sub     rsp, 38h
0x180012349  mov     rdi, r8
0x18001234c  mov     rsi, rdx
0x18001234f  mov     rbx, rcx
0x180012352  mov     rcx, cs:WPP_GLOBAL_Control
0x180012359  lea     rbp, WPP_GLOBAL_Control
0x180012360  cmp     rcx, rbp
0x180012363  jz      short loc_180012386
0x180012365  test    byte ptr [rcx+1Ch], 1
0x180012369  jz      short loc_180012386
0x18001236b  cmp     byte ptr [rcx+19h], 5
0x18001236f  jb      short loc_180012386
0x180012371  mov     rcx, [rcx+10h]
0x180012375  lea     r8, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids
0x18001237c  mov     edx, 12h
0x180012381  call    WPP_SF_
0x180012386  lea     rdx, aGlobals; "Globals"
0x18001238d  mov     rcx, rbx; this
0x180012390  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x180012395  mov     ebx, eax
0x180012397  test    eax, eax
0x180012399  js      short loc_180012419
0x18001239b  lea     rdx, aFactory; "Factory"
0x1800123a2  mov     rcx, rsi; this
0x1800123a5  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800123aa  mov     ebx, eax
0x1800123ac  test    eax, eax
0x1800123ae  js      short loc_180012419
0x1800123b0  lea     rdx, aCircuit; "Circuit"
0x1800123b7  mov     rcx, rdi; this
0x1800123ba  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x1800123bf  mov     ebx, eax
0x1800123c1  test    eax, eax
0x1800123c3  js      short loc_180012419
0x1800123c5  mov     rdx, rdi
0x1800123c8  mov     rcx, rsi
0x1800123cb  not     rdx; struct Apx::ApfCircuit *
0x1800123ce  not     rcx; this
0x1800123d1  call    ?RemoveCircuit@ApfCircuitFactory@Apx@@QEAAJPEAVApfCircuit@2@@Z; Apx::ApfCircuitFactory::RemoveCircuit(Apx::ApfCircuit *)
0x1800123d6  mov     ebx, eax
0x1800123d8  test    eax, eax
0x1800123da  jns     short loc_180012417
0x1800123dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123e3  cmp     rcx, rbp
0x1800123e6  jz      short loc_180012446
0x1800123e8  test    byte ptr [rcx+1Ch], 20h
0x1800123ec  jz      short loc_180012420
0x1800123ee  cmp     byte ptr [rcx+19h], 2
0x1800123f2  jb      short loc_180012420
0x1800123f4  mov     rcx, [rcx+10h]
0x1800123f8  lea     r8, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids
0x1800123ff  mov     [rsp+58h+var_30], eax
0x180012403  mov     edx, 13h
0x180012408  mov     r9, rsi
0x18001240b  mov     [rsp+58h+var_38], rdi
0x180012410  call    WPP_SF_qqd
0x180012415  jmp     short loc_180012419
0x180012417  xor     ebx, ebx
0x180012419  mov     rcx, cs:WPP_GLOBAL_Control
0x180012420  cmp     rcx, rbp
0x180012423  jz      short loc_180012446
0x180012425  test    byte ptr [rcx+1Ch], 1
0x180012429  jz      short loc_180012446
0x18001242b  cmp     byte ptr [rcx+19h], 5
0x18001242f  jb      short loc_180012446
0x180012431  mov     rcx, [rcx+10h]
0x180012435  lea     r8, WPP_f146969c834c395fcb3856bfb63c0f03_Traceguids
0x18001243c  mov     edx, 14h
0x180012441  call    WPP_SF_
0x180012446  mov     eax, ebx
0x180012448  add     rsp, 38h
0x18001244c  pop     rdi
0x18001244d  pop     rsi
0x18001244e  pop     rbp
0x18001244f  pop     rbx
0x180012450  retn
```
