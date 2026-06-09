# CspDeleteFile

- ea: `0x18001dd04`
- end: `0x18001de20`
- name: `CspDeleteFile`
- size: `284`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180012fa0`
- `0x18001e9b8`
- `0x180020e28`

## callees

- `0x180017bac`
- `0x18001cba0`
- `0x18001dd04`
- `0x18001f3a4`
- `0x180021b48`
- `0x180021ddc`
- `0x18002cfa0`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall CspDeleteFile(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  __int64 v6; // rdx
  unsigned int String; // ebx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // r9d
  unsigned __int16 v13[264]; // [rsp+40h] [rbp-228h] BYREF

  String = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !String )
  {
    String = I_BuildFileCacheQueryString(v13, v6, "mscp", a4);
    if ( !String )
    {
      v8 = DeleteCachedCardData(a1, v13);
      if ( v8 != 1168 )
        String = v8;
      if ( !String )
      {
        v10 = *(_QWORD *)(a1 + 8);
        if ( v10 )
        {
          return (*(unsigned int (__fastcall **)(_QWORD, const char *, char *, _QWORD))(v10 + 264))(
                   *(_QWORD *)(a1 + 8),
                   "mscp",
                   a4,
                   0);
        }
        else
        {
          String = 87;
          WppTraceIndent(v9, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_ss(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
              v11,
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
0x18001dd04  mov     [rsp+arg_8], rbx
0x18001dd09  mov     [rsp+arg_10], rsi
0x18001dd0e  push    rdi
0x18001dd0f  sub     rsp, 260h
0x18001dd16  mov     rax, cs:__security_cookie
0x18001dd1d  xor     rax, rsp
0x18001dd20  mov     [rsp+268h+var_18], rax
0x18001dd28  xor     eax, eax
0x18001dd2a  lea     r8, [rsp+268h+var_238]
0x18001dd2f  mov     rsi, r9
0x18001dd32  mov     [rsp+268h+var_238], eax
0x18001dd36  mov     rdi, rcx
0x18001dd39  mov     [rsp+268h+var_234], ax
0x18001dd3e  lea     edx, [rax+4]
0x18001dd41  call    CspIncrementCacheFreshness
0x18001dd46  mov     ebx, eax
0x18001dd48  test    eax, eax
0x18001dd4a  jnz     loc_18001DDF9
0x18001dd50  mov     r9, rsi; char *
0x18001dd53  lea     r8, aMscp; "mscp"
0x18001dd5a  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001dd5f  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18001dd64  mov     ebx, eax
0x18001dd66  test    eax, eax
0x18001dd68  jnz     loc_18001DDF9
0x18001dd6e  lea     rdx, [rsp+268h+var_228]
0x18001dd73  mov     rcx, rdi
0x18001dd76  call    DeleteCachedCardData
0x18001dd7b  cmp     eax, 490h
0x18001dd80  cmovnz  ebx, eax
0x18001dd83  test    ebx, ebx
0x18001dd85  jnz     short loc_18001DDF9
0x18001dd87  mov     rax, [rdi+8]
0x18001dd8b  test    rax, rax
0x18001dd8e  jnz     short loc_18001DDDB
0x18001dd90  lea     edx, [rax+2]
0x18001dd93  lea     ebx, [rax+57h]
0x18001dd96  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001dd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dda2  lea     rax, WPP_GLOBAL_Control
0x18001dda9  cmp     rcx, rax
0x18001ddac  jz      short loc_18001DDF9
0x18001ddae  test    byte ptr [rcx+1Ch], 1
0x18001ddb2  jz      short loc_18001DDF9
0x18001ddb4  cmp     byte ptr [rcx+19h], 2
0x18001ddb8  jb      short loc_18001DDF9
0x18001ddba  mov     rcx, [rcx+10h]
0x18001ddbe  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001ddc5  lea     edx, [rbx-3Ah]
0x18001ddc8  mov     [rsp+268h+var_248], rax
0x18001ddcd  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001ddd4  call    WPP_SF_ss
0x18001ddd9  jmp     short loc_18001DDF9
0x18001dddb  mov     rcx, rax
0x18001ddde  lea     rdx, aMscp; "mscp"
0x18001dde5  mov     rax, [rax+108h]
0x18001ddec  xor     r9d, r9d
0x18001ddef  mov     r8, rsi
0x18001ddf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddf7  mov     ebx, eax
0x18001ddf9  mov     eax, ebx
0x18001ddfb  mov     rcx, [rsp+268h+var_18]
0x18001de03  xor     rcx, rsp; StackCookie
0x18001de06  call    __security_check_cookie
0x18001de0b  lea     r11, [rsp+268h+var_8]
0x18001de13  mov     rbx, [r11+18h]
0x18001de17  mov     rsi, [r11+20h]
0x18001de1b  mov     rsp, r11
0x18001de1e  pop     rdi
0x18001de1f  retn
```
