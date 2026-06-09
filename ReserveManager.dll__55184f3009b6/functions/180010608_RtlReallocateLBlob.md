# RtlReallocateLBlob

- ea: `0x180010608`
- end: `0x18001076e`
- name: `RtlReallocateLBlob`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f82c`

## callees

- `0x18000fafc`
- `0x180010608`
- `0x180010774`
- `0x1800107b4`

## string_xrefs

- `0x1800106a7`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x1800106fd`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
__int64 __fastcall RtlReallocateLBlob(__int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  const char *v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rax
  __int64 StringRoutine; // rax
  const char *v9; // rax
  const char *v11; // [rsp+20h] [rbp-20h] BYREF
  const char *v12; // [rsp+28h] [rbp-18h]
  __int64 v13; // [rsp+30h] [rbp-10h]
  const char *v14; // [rsp+38h] [rbp-8h]

  if ( a3 )
  {
    v6 = a3[2];
    if ( !v6 && *a3 || (v7 = a3[1], *a3 > v7) )
    {
      v13 = 131;
      v11 = "onecore\\base\\lstring\\lblob.cpp";
      v12 = "RtlReallocateLBlob";
      v5 = "::RtlIsLBlobValid(Blob)";
      goto LABEL_17;
    }
    if ( v6 )
    {
      if ( v7 >= a2 )
        return 0;
      StringRoutine = anonymous_namespace_::OurRtlReallocateStringRoutine(a2);
      if ( !StringRoutine )
      {
        v13 = 148;
        v11 = "onecore\\base\\lstring\\lblob.cpp";
        v12 = "RtlReallocateLBlob";
        v9 = "Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)";
LABEL_10:
        v14 = v9;
        RtlReportErrorOrigination(&v11, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        return 3221225495LL;
      }
    }
    else
    {
      StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine(a2);
      if ( !StringRoutine )
      {
        v13 = 153;
        v11 = "onecore\\base\\lstring\\lblob.cpp";
        v12 = "RtlReallocateLBlob";
        v9 = "Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))";
        goto LABEL_10;
      }
    }
    a3[2] = StringRoutine;
    a3[1] = a2;
    if ( *a3 > a2 )
      *a3 = a2;
    return 0;
  }
  v13 = 130;
  v11 = "onecore\\base\\lstring\\lblob.cpp";
  v12 = "RtlReallocateLBlob";
  v5 = "Not-null check failed: Blob";
LABEL_17:
  v14 = v5;
  RtlReportErrorOrigination(&v11, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180010608  mov     [rsp-8+arg_0], rbx
0x18001060d  mov     [rsp-8+arg_18], rdi
0x180010612  push    rbp
0x180010613  mov     rbp, rsp
0x180010616  sub     rsp, 40h
0x18001061a  mov     rbx, r8
0x18001061d  mov     rdi, rdx
0x180010620  test    r8, r8
0x180010623  jnz     short loc_18001064F
0x180010625  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18001062c  mov     [rbp+var_10], 82h
0x180010634  mov     [rbp+var_20], rax
0x180010638  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18001063f  mov     [rbp+var_18], rax
0x180010643  lea     rax, aNotNullCheckFa_12; "Not-null check failed: Blob"
0x18001064a  jmp     loc_18001073F
0x18001064f  mov     rdx, [r8+10h]
0x180010653  test    rdx, rdx
0x180010656  jnz     short loc_180010661
0x180010658  cmp     [r8], rdx
0x18001065b  jnz     loc_18001071A
0x180010661  mov     rax, [r8+8]
0x180010665  cmp     [r8], rax
0x180010668  ja      loc_18001071A
0x18001066e  test    rdx, rdx
0x180010671  jz      short loc_1800106D2
0x180010673  cmp     rax, rdi
0x180010676  jnb     loc_180010716
0x18001067c  mov     rcx, rdi
0x18001067f  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x180010684  test    rax, rax
0x180010687  jnz     short loc_180010706
0x180010689  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180010690  mov     [rbp+var_10], 94h
0x180010698  mov     [rbp+var_20], rax
0x18001069c  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x1800106a3  mov     [rbp+var_18], rax
0x1800106a7  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x1800106ae  mov     r8d, 0C0000017h
0x1800106b4  mov     [rbp+var_8], rax
0x1800106b8  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800106bf  lea     rcx, [rbp+var_20]
0x1800106c3  call    RtlReportErrorOrigination
0x1800106c8  mov     eax, 0C0000017h
0x1800106cd  jmp     loc_18001075E
0x1800106d2  mov     rcx, rdi
0x1800106d5  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x1800106da  test    rax, rax
0x1800106dd  jnz     short loc_180010706
0x1800106df  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1800106e6  mov     [rbp+var_10], 99h
0x1800106ee  mov     [rbp+var_20], rax
0x1800106f2  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x1800106f9  mov     [rbp+var_18], rax
0x1800106fd  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x180010704  jmp     short loc_1800106AE
0x180010706  mov     [rbx+10h], rax
0x18001070a  mov     [rbx+8], rdi
0x18001070e  cmp     [rbx], rdi
0x180010711  jbe     short loc_180010716
0x180010713  mov     [rbx], rdi
0x180010716  xor     eax, eax
0x180010718  jmp     short loc_18001075E
0x18001071a  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180010721  mov     [rbp+var_10], 83h
0x180010729  mov     [rbp+var_20], rax
0x18001072d  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x180010734  mov     [rbp+var_18], rax
0x180010738  lea     rax, aRtlislblobvali; "::RtlIsLBlobValid(Blob)"
0x18001073f  mov     r8d, 0C000000Dh
0x180010745  mov     [rbp+var_8], rax
0x180010749  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180010750  lea     rcx, [rbp+var_20]
0x180010754  call    RtlReportErrorOrigination
0x180010759  mov     eax, 0C000000Dh
0x18001075e  mov     rbx, [rsp+40h+arg_0]
0x180010763  mov     rdi, [rsp+40h+arg_18]
0x180010768  add     rsp, 40h
0x18001076c  pop     rbp
0x18001076d  retn
```
