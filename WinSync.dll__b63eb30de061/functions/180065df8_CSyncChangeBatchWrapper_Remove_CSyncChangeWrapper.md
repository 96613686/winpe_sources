# CSyncChangeBatchWrapper::Remove(CSyncChangeWrapper *)

- ea: `0x180065df8`
- end: `0x180065ef2`
- name: `?Remove@CSyncChangeBatchWrapper@@QEAAJPEAVCSyncChangeWrapper@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *__hidden this, struct CSyncChangeWrapper *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800383f4`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180065df8`
- `0x180065ef8`

## string_xrefs

- `0x180065e2c`: `CSyncChangeBatchWrapper::Remove`
- `0x180065ec9`: `CSyncChangeBatchWrapper::Remove`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::Remove(CSyncChangeBatchWrapper *this, struct CSyncChangeWrapper *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rbp
  struct CSyncChangeWrapper **v8; // rdx
  int v9; // eax
  __int64 i; // rdx
  unsigned int v11; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::Remove");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    if ( (v6 = *((_QWORD *)this + 3), v5 = -2147217379, v7 = *((_QWORD *)this + 4), !v6)
      || a2 != *(struct CSyncChangeWrapper **)v6 && ((v8 = *(struct CSyncChangeWrapper ***)(v6 + 16)) == 0 || *v8 != a2)
      || (v9 = CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(*((_QWORD *)this + 4)),
          v4 = (PVOID *)WPP_GLOBAL_Control,
          v5 = v9,
          v9 < 0) )
    {
      for ( i = *(_QWORD *)(v7 + 16); i; i = *(_QWORD *)(i + 8) )
      {
        if ( a2 == *(struct CSyncChangeWrapper **)i )
        {
          v11 = CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(v7);
          v4 = (PVOID *)WPP_GLOBAL_Control;
          v5 = v11;
          break;
        }
      }
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      26,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::Remove",
      v5);
  return v5;
}

```

## disassembly

```asm
0x180065df8  push    rbx
0x180065dfa  push    rbp
0x180065dfb  push    rsi
0x180065dfc  push    rdi
0x180065dfd  push    r14
0x180065dff  sub     rsp, 30h
0x180065e03  mov     rdi, rdx
0x180065e06  mov     rsi, rcx
0x180065e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e10  lea     r14, WPP_GLOBAL_Control
0x180065e17  cmp     rcx, r14
0x180065e1a  jz      short loc_180065E4B
0x180065e1c  test    byte ptr [rcx+1Ch], 8
0x180065e20  jz      short loc_180065E4B
0x180065e22  cmp     byte ptr [rcx+19h], 5
0x180065e26  jb      short loc_180065E4B
0x180065e28  mov     rcx, [rcx+10h]
0x180065e2c  lea     r9, aCsyncchangebat_24; "CSyncChangeBatchWrapper::Remove"
0x180065e33  mov     edx, 19h
0x180065e38  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180065e3f  call    WPP_SF_s
0x180065e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e4b  mov     ebx, 80004003h
0x180065e50  test    rdi, rdi
0x180065e53  jz      short loc_180065EB4
0x180065e55  mov     rdx, [rsi+18h]
0x180065e59  mov     ebx, 8004101Dh
0x180065e5e  mov     rbp, [rsi+20h]
0x180065e62  test    rdx, rdx
0x180065e65  jz      short loc_180065E8F
0x180065e67  cmp     rdi, [rdx]
0x180065e6a  jz      short loc_180065E7A
0x180065e6c  mov     rdx, [rdx+10h]
0x180065e70  test    rdx, rdx
0x180065e73  jz      short loc_180065E8F
0x180065e75  cmp     [rdx], rdi
0x180065e78  jnz     short loc_180065E8F
0x180065e7a  mov     rcx, rbp
0x180065e7d  call    ?RemoveElement@?$CollectionManager@VCSyncChangeUnitWrapper@@@@QEAAJPEAU?$CollectionElement@VCSyncChangeUnitWrapper@@@@@Z; CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(CollectionElement<CSyncChangeUnitWrapper> *)
0x180065e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e89  mov     ebx, eax
0x180065e8b  test    eax, eax
0x180065e8d  jns     short loc_180065EB4
0x180065e8f  mov     rdx, [rbp+10h]
0x180065e93  test    rdx, rdx
0x180065e96  jz      short loc_180065EB4
0x180065e98  cmp     rdi, [rdx]
0x180065e9b  jz      short loc_180065EA3
0x180065e9d  mov     rdx, [rdx+8]
0x180065ea1  jmp     short loc_180065E93
0x180065ea3  mov     rcx, rbp
0x180065ea6  call    ?RemoveElement@?$CollectionManager@VCSyncChangeUnitWrapper@@@@QEAAJPEAU?$CollectionElement@VCSyncChangeUnitWrapper@@@@@Z; CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(CollectionElement<CSyncChangeUnitWrapper> *)
0x180065eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180065eb2  mov     ebx, eax
0x180065eb4  cmp     rcx, r14
0x180065eb7  jz      short loc_180065EE5
0x180065eb9  test    byte ptr [rcx+1Ch], 8
0x180065ebd  jz      short loc_180065EE5
0x180065ebf  cmp     byte ptr [rcx+19h], 5
0x180065ec3  jb      short loc_180065EE5
0x180065ec5  mov     rcx, [rcx+10h]
0x180065ec9  lea     r9, aCsyncchangebat_24; "CSyncChangeBatchWrapper::Remove"
0x180065ed0  mov     edx, 1Ah
0x180065ed5  mov     [rsp+58h+var_38], ebx
0x180065ed9  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180065ee0  call    WPP_SF_sD
0x180065ee5  mov     eax, ebx
0x180065ee7  add     rsp, 30h
0x180065eeb  pop     r14
0x180065eed  pop     rdi
0x180065eee  pop     rsi
0x180065eef  pop     rbp
0x180065ef0  pop     rbx
0x180065ef1  retn
```
