# RtlReallocateLBlob

- ea: `0x140026c54`
- end: `0x140026dac`
- name: `RtlReallocateLBlob`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140026694`

## callees

- `0x140002360`
- `0x140026548`
- `0x140026c2c`
- `0x140026c54`
- `0x140026db4`
- `0x140026df4`

## string_xrefs

- `0x140026d38`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x140026d75`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
__int64 __fastcall RtlReallocateLBlob(__int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  const char *v5; // rax
  __int64 v6; // r8
  __int64 v8; // r8
  __int64 StringRoutine; // rax
  const char *v10; // [rsp+20h] [rbp-30h] BYREF
  const char *v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  int v14; // [rsp+40h] [rbp-10h] BYREF

  v14 = 0;
  if ( !a3 )
  {
    v12 = 130;
    v10 = "onecore\\base\\lstring\\lblob.cpp";
    v11 = "RtlReallocateLBlob";
    v5 = "Not-null check failed: Blob";
LABEL_3:
    v6 = 3221225485LL;
LABEL_4:
    v13 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v14,
             &v10,
             v6);
  }
  if ( !(unsigned __int8)RtlIsLBlobValid(a3) )
  {
    v12 = 131;
    v10 = "onecore\\base\\lstring\\lblob.cpp";
    v11 = "RtlReallocateLBlob";
    v5 = "::RtlIsLBlobValid(Blob)";
    goto LABEL_3;
  }
  if ( !*(_QWORD *)(v8 + 16) )
  {
    StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine(a2);
    if ( !StringRoutine )
    {
      v12 = 153;
      v10 = "onecore\\base\\lstring\\lblob.cpp";
      v11 = "RtlReallocateLBlob";
      v5 = "Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))";
      goto LABEL_11;
    }
    goto LABEL_14;
  }
  if ( *(_QWORD *)(v8 + 8) < a2 )
  {
    StringRoutine = anonymous_namespace_::OurRtlReallocateStringRoutine(a2);
    if ( !StringRoutine )
    {
      v12 = 148;
      v10 = "onecore\\base\\lstring\\lblob.cpp";
      v11 = "RtlReallocateLBlob";
      v5 = "Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)";
LABEL_11:
      v6 = 3221225495LL;
      goto LABEL_4;
    }
LABEL_14:
    a3[2] = StringRoutine;
    a3[1] = a2;
    if ( *a3 > a2 )
      *a3 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x140026c54  mov     [rsp-8+arg_0], rbx
0x140026c59  mov     [rsp-8+arg_18], rdi
0x140026c5e  push    rbp
0x140026c5f  mov     rbp, rsp
0x140026c62  sub     rsp, 50h
0x140026c66  mov     rax, cs:__security_cookie
0x140026c6d  xor     rax, rsp
0x140026c70  mov     [rbp+var_8], rax
0x140026c74  mov     [rbp+var_10], 0
0x140026c7b  mov     rbx, r8
0x140026c7e  mov     rdi, rdx
0x140026c81  test    r8, r8
0x140026c84  jnz     short loc_140026CC7
0x140026c86  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140026c8d  mov     [rbp+var_20], 82h
0x140026c95  mov     [rbp+var_30], rax
0x140026c99  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x140026ca0  mov     [rbp+var_28], rax
0x140026ca4  lea     rax, aNotNullCheckFa_3; "Not-null check failed: Blob"
0x140026cab  mov     r8d, 0C000000Dh
0x140026cb1  lea     rdx, [rbp+var_30]
0x140026cb5  mov     [rbp+var_18], rax
0x140026cb9  lea     rcx, [rbp+var_10]
0x140026cbd  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026cc2  jmp     loc_140026D90
0x140026cc7  mov     rcx, rbx
0x140026cca  call    RtlIsLBlobValid
0x140026ccf  test    al, al
0x140026cd1  jnz     short loc_140026CFA
0x140026cd3  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140026cda  mov     [rbp+var_20], 83h
0x140026ce2  mov     [rbp+var_30], rax
0x140026ce6  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x140026ced  mov     [rbp+var_28], rax
0x140026cf1  lea     rax, aRtlislblobvali; "::RtlIsLBlobValid(Blob)"
0x140026cf8  jmp     short loc_140026CAB
0x140026cfa  mov     rdx, [r8+10h]
0x140026cfe  test    rdx, rdx
0x140026d01  jz      short loc_140026D4A
0x140026d03  cmp     [r8+8], rdi
0x140026d07  jnb     loc_140026D8E
0x140026d0d  mov     rcx, rdi
0x140026d10  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x140026d15  test    rax, rax
0x140026d18  jnz     short loc_140026D7E
0x140026d1a  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140026d21  mov     [rbp+var_20], 94h
0x140026d29  mov     [rbp+var_30], rax
0x140026d2d  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x140026d34  mov     [rbp+var_28], rax
0x140026d38  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x140026d3f  mov     r8d, 0C0000017h
0x140026d45  jmp     loc_140026CB1
0x140026d4a  mov     rcx, rdi
0x140026d4d  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x140026d52  test    rax, rax
0x140026d55  jnz     short loc_140026D7E
0x140026d57  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x140026d5e  mov     [rbp+var_20], 99h
0x140026d66  mov     [rbp+var_30], rax
0x140026d6a  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x140026d71  mov     [rbp+var_28], rax
0x140026d75  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x140026d7c  jmp     short loc_140026D3F
0x140026d7e  mov     [rbx+10h], rax
0x140026d82  mov     [rbx+8], rdi
0x140026d86  cmp     [rbx], rdi
0x140026d89  jbe     short loc_140026D8E
0x140026d8b  mov     [rbx], rdi
0x140026d8e  xor     eax, eax
0x140026d90  mov     rcx, [rbp+var_8]
0x140026d94  xor     rcx, rsp; StackCookie
0x140026d97  call    __security_check_cookie
0x140026d9c  mov     rbx, [rsp+50h+arg_0]
0x140026da1  mov     rdi, [rsp+50h+arg_18]
0x140026da6  add     rsp, 50h
0x140026daa  pop     rbp
0x140026dab  retn
```
