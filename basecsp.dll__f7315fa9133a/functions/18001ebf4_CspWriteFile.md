# CspWriteFile

- ea: `0x18001ebf4`
- end: `0x18001ed5e`
- name: `CspWriteFile`
- size: `362`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180012fa0`
- `0x18001fadc`
- `0x18001fca8`
- `0x180020144`
- `0x180020e28`

## callees

- `0x180017bac`
- `0x18001cba0`
- `0x18001ebf4`
- `0x18001f3a4`
- `0x180021928`
- `0x180021b48`
- `0x180021ddc`
- `0x18002cfa0`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall CspWriteFile(__int64 a1, __int64 a2, char *a3, __int64 a4, void *a5, unsigned int a6)
{
  __int64 v8; // rdx
  unsigned int String; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // r9d
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-238h] BYREF

  String = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !String )
  {
    String = I_BuildFileCacheQueryString(v15, v8, "mscp", a3);
    if ( !String )
    {
      v10 = DeleteCachedCardData(a1, v15);
      if ( v10 != 1168 )
        String = v10;
      if ( !String )
      {
        v12 = *(_QWORD *)(a1 + 8);
        if ( v12 )
        {
          String = (*(__int64 (__fastcall **)(_QWORD, const char *, char *, _QWORD, void *, unsigned int))(v12 + 256))(
                     *(_QWORD *)(a1 + 8),
                     "mscp",
                     a3,
                     0,
                     a5,
                     a6);
          if ( !String )
            return (unsigned int)AddCachedCardData(a1, v15, 4, 1, a5, a6, 0);
        }
        else
        {
          String = 87;
          WppTraceIndent(v11, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_ss(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
              v13,
              (__int64)"pCardState->pCardData");
          }
        }
      }
    }
  }
  return String;
}

```

## disassembly

```asm
0x18001ebf4  mov     [rsp+arg_8], rbx
0x18001ebf9  mov     [rsp+arg_18], rbp
0x18001ebfe  push    rsi
0x18001ebff  push    rdi
0x18001ec00  push    r14
0x18001ec02  sub     rsp, 270h
0x18001ec09  mov     rax, cs:__security_cookie
0x18001ec10  xor     rax, rsp
0x18001ec13  mov     [rsp+288h+var_28], rax
0x18001ec1b  mov     r14, [rsp+288h+arg_20]
0x18001ec23  xor     eax, eax
0x18001ec25  mov     rbp, r8
0x18001ec28  mov     [rsp+288h+var_248], eax
0x18001ec2c  lea     r8, [rsp+288h+var_248]
0x18001ec31  mov     [rsp+288h+var_244], ax
0x18001ec36  mov     rdi, rcx
0x18001ec39  lea     edx, [rax+4]
0x18001ec3c  call    CspIncrementCacheFreshness
0x18001ec41  mov     ebx, eax
0x18001ec43  test    eax, eax
0x18001ec45  jnz     loc_18001ED34
0x18001ec4b  mov     r9, rbp; char *
0x18001ec4e  lea     r8, aMscp; "mscp"
0x18001ec55  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x18001ec5a  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18001ec5f  mov     ebx, eax
0x18001ec61  test    eax, eax
0x18001ec63  jnz     loc_18001ED34
0x18001ec69  lea     rdx, [rsp+288h+var_238]
0x18001ec6e  mov     rcx, rdi
0x18001ec71  call    DeleteCachedCardData
0x18001ec76  cmp     eax, 490h
0x18001ec7b  cmovnz  ebx, eax
0x18001ec7e  test    ebx, ebx
0x18001ec80  jnz     loc_18001ED34
0x18001ec86  mov     rax, [rdi+8]
0x18001ec8a  test    rax, rax
0x18001ec8d  jnz     short loc_18001ECDE
0x18001ec8f  lea     edx, [rax+2]
0x18001ec92  lea     ebx, [rax+57h]
0x18001ec95  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ec9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eca1  lea     rax, WPP_GLOBAL_Control
0x18001eca8  cmp     rcx, rax
0x18001ecab  jz      loc_18001ED34
0x18001ecb1  test    byte ptr [rcx+1Ch], 1
0x18001ecb5  jz      short loc_18001ED34
0x18001ecb7  cmp     byte ptr [rcx+19h], 2
0x18001ecbb  jb      short loc_18001ED34
0x18001ecbd  mov     rcx, [rcx+10h]
0x18001ecc1  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001ecc8  lea     edx, [rbx-3Bh]
0x18001eccb  mov     [rsp+288h+var_268], rax
0x18001ecd0  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001ecd7  call    WPP_SF_ss
0x18001ecdc  jmp     short loc_18001ED34
0x18001ecde  mov     esi, [rsp+288h+arg_28]
0x18001ece5  lea     rdx, aMscp; "mscp"
0x18001ecec  mov     rcx, rax
0x18001ecef  mov     [rsp+288h+var_260], esi
0x18001ecf3  mov     rax, [rax+100h]
0x18001ecfa  xor     r9d, r9d
0x18001ecfd  mov     r8, rbp
0x18001ed00  mov     [rsp+288h+var_268], r14
0x18001ed05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed0a  mov     ebx, eax
0x18001ed0c  test    eax, eax
0x18001ed0e  jnz     short loc_18001ED34
0x18001ed10  mov     [rsp+288h+var_258], eax
0x18001ed14  lea     r9d, [rax+1]
0x18001ed18  mov     [rsp+288h+var_260], esi
0x18001ed1c  lea     r8d, [rax+4]
0x18001ed20  lea     rdx, [rsp+288h+var_238]
0x18001ed25  mov     [rsp+288h+var_268], r14
0x18001ed2a  mov     rcx, rdi
0x18001ed2d  call    AddCachedCardData
0x18001ed32  mov     ebx, eax
0x18001ed34  mov     eax, ebx
0x18001ed36  mov     rcx, [rsp+288h+var_28]
0x18001ed3e  xor     rcx, rsp; StackCookie
0x18001ed41  call    __security_check_cookie
0x18001ed46  lea     r11, [rsp+288h+var_18]
0x18001ed4e  mov     rbx, [r11+28h]
0x18001ed52  mov     rbp, [r11+38h]
0x18001ed56  mov     rsp, r11
0x18001ed59  pop     r14
0x18001ed5b  pop     rdi
0x18001ed5c  pop     rsi
0x18001ed5d  retn
```
