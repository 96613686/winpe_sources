# EqualityTwoNodeSetsExpression::ProcessNavigation(XPathNavigatorInternal &,bool,StringTable &,StringTable &,bool &)

- ea: `0x18000ee14`
- end: `0x18000eecb`
- name: `?ProcessNavigation@EqualityTwoNodeSetsExpression@@CAJAEAVXPathNavigatorInternal@@_NAEAVStringTable@@2AEA_N@Z`
- size: `183`
- prototype: `static int(struct XPathNavigatorInternal *, bool, struct StringTable *, struct StringTable *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e8c0`

## callees

- `0x18000e594`
- `0x18000ee14`
- `0x180011540`
- `0x180011624`

## pseudocode

```c
int __fastcall EqualityTwoNodeSetsExpression::ProcessNavigation(
        struct XPathNavigatorInternal *a1,
        char a2,
        struct StringTable *a3,
        struct StringTable *a4,
        bool *a5)
{
  bool *v5; // r14
  int result; // eax
  int v10; // ebx
  int v11; // ecx
  unsigned __int16 *v12; // [rsp+20h] [rbp-38h] BYREF

  v5 = a5;
  v12 = 0;
  *a5 = 0;
  result = XPathNavigatorInternal::GetValue(a1, (const unsigned __int16 **)&v12);
  v10 = result;
  if ( result < 0 )
    return result;
  if ( a2 )
  {
    if ( !StringTable::Contains(a4, v12) )
      goto LABEL_4;
LABEL_11:
    *v5 = 1;
    return v10;
  }
  v11 = *((_DWORD *)a4 + 5);
  if ( v11 && (v11 != 1 || !StringTable::Contains(a4, v12)) )
    goto LABEL_11;
LABEL_4:
  if ( StringTable::Contains(a3, v12) )
    return v10;
  a5 = 0;
  result = StringTable::Add(a3, v12, (const unsigned __int16 **)&a5);
  v10 = result;
  if ( result >= 0 )
    return v10;
  return result;
}

```

## disassembly

```asm
0x18000ee14  push    rbx
0x18000ee16  push    rbp
0x18000ee17  push    rsi
0x18000ee18  push    rdi
0x18000ee19  push    r14
0x18000ee1b  sub     rsp, 30h
0x18000ee1f  mov     r14, [rsp+58h+arg_20]
0x18000ee27  mov     bpl, dl
0x18000ee2a  lea     rdx, [rsp+58h+var_38]; unsigned __int16 **
0x18000ee2f  mov     [rsp+58h+var_38], 0
0x18000ee38  mov     rdi, r9
0x18000ee3b  mov     rsi, r8
0x18000ee3e  mov     byte ptr [r14], 0
0x18000ee42  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000ee47  mov     ebx, eax
0x18000ee49  test    eax, eax
0x18000ee4b  js      short loc_18000EE9D
0x18000ee4d  test    bpl, bpl
0x18000ee50  jz      short loc_18000EEA8
0x18000ee52  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x18000ee57  mov     rcx, rdi; this
0x18000ee5a  call    ?Contains@StringTable@@QEAA_NPEBG@Z; StringTable::Contains(ushort const *)
0x18000ee5f  test    al, al
0x18000ee61  jnz     short loc_18000EEC5
0x18000ee63  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x18000ee68  mov     rcx, rsi; this
0x18000ee6b  call    ?Contains@StringTable@@QEAA_NPEBG@Z; StringTable::Contains(ushort const *)
0x18000ee70  test    al, al
0x18000ee72  jnz     short loc_18000EE9B
0x18000ee74  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x18000ee79  lea     r8, [rsp+58h+arg_20]; unsigned __int16 **
0x18000ee81  mov     rcx, rsi; this
0x18000ee84  mov     [rsp+58h+arg_20], 0
0x18000ee90  call    ?Add@StringTable@@QEAAJPEBGPEAPEBG@Z; StringTable::Add(ushort const *,ushort const * *)
0x18000ee95  mov     ebx, eax
0x18000ee97  test    eax, eax
0x18000ee99  js      short loc_18000EE9D
0x18000ee9b  mov     eax, ebx
0x18000ee9d  add     rsp, 30h
0x18000eea1  pop     r14
0x18000eea3  pop     rdi
0x18000eea4  pop     rsi
0x18000eea5  pop     rbp
0x18000eea6  pop     rbx
0x18000eea7  retn
0x18000eea8  mov     ecx, [rdi+14h]
0x18000eeab  test    ecx, ecx
0x18000eead  jz      short loc_18000EE63
0x18000eeaf  cmp     ecx, 1
0x18000eeb2  jnz     short loc_18000EEC5
0x18000eeb4  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x18000eeb9  mov     rcx, rdi; this
0x18000eebc  call    ?Contains@StringTable@@QEAA_NPEBG@Z; StringTable::Contains(ushort const *)
0x18000eec1  test    al, al
0x18000eec3  jnz     short loc_18000EE63
0x18000eec5  mov     byte ptr [r14], 1
0x18000eec9  jmp     short loc_18000EE9B
```
