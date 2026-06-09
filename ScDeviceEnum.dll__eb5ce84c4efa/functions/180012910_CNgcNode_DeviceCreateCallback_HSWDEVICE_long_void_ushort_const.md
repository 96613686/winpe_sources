# CNgcNode::_DeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180012910`
- end: `0x180012a62`
- name: `?_DeviceCreateCallback@CNgcNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `338`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, char *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x180009970`
- `0x180011a6c`
- `0x180011d5c`
- `0x180011e00`
- `0x180012910`
- `0x18001e020`

## string_xrefs

- `0x180012945`: `CNgcNode::_DeviceCreateCallback`

## pseudocode

```c
void __fastcall CNgcNode::_DeviceCreateCallback(struct HSWDEVICE__ *a1, int a2, char *a3, const unsigned __int16 *a4)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v9; // [rsp+30h] [rbp-78h] BYREF
  int v10; // [rsp+34h] [rbp-74h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-70h] BYREF
  __int16 v12; // [rsp+48h] [rbp-60h]
  char *v13; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v14; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v15[3]; // [rsp+60h] [rbp-48h] BYREF
  char v16[32]; // [rsp+78h] [rbp-30h] BYREF

  v9 = a2;
  v10 = 0;
  strcpy(v16, "CNgcNode::_DeviceCreateCallback");
  v15[0] = v16;
  v15[1] = &v10;
  v15[2] = &v9;
  lambda_f2b522d031acac6736ee111016a9fe68_::operator()(v15);
  v10 = 1;
  v14 = v15;
  v13 = a3;
  v11[0] = &v13;
  v11[1] = &v9;
  v12 = 258;
  if ( v9 >= 0 )
  {
    if ( *a4 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a4[v7] );
    }
    else
    {
      v7 = 0;
    }
    try
    {
      std::wstring::assign((_QWORD *)a3 + 3, (unsigned __int64)a4, v7);
    }
    catch ( std::bad_alloc )
    {
      v9 = -2147024882;
      WppTraceIndent(v8, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
          (int)WPP_pszIndent,
          v9);
      }
    }
  }
  else
  {
    WppTraceIndent(v6, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
        (int)WPP_pszIndent,
        v9);
    }
  }
  wil::details::ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979___::operator()(v11);
  WppTraceUnwinder__lambda_f2b522d031acac6736ee111016a9fe68____::_WppTraceUnwinder__lambda_f2b522d031acac6736ee111016a9fe68____(&v14);
}

```

## disassembly

```asm
0x180012910  mov     r11, rsp
0x180012913  mov     [r11+8], rbx
0x180012917  mov     [r11+10h], rsi
0x18001291b  push    rdi
0x18001291c  sub     rsp, 0A0h
0x180012923  mov     rax, cs:__security_cookie
0x18001292a  xor     rax, rsp
0x18001292d  mov     [rsp+0A8h+var_10], rax
0x180012935  mov     rbx, r9
0x180012938  mov     rdi, r8
0x18001293b  mov     [rsp+0A8h+var_78], edx
0x18001293f  xor     esi, esi
0x180012941  mov     [rsp+0A8h+var_74], esi
0x180012945  movups  xmm0, xmmword ptr cs:aCngcnodeDevice; "CNgcNode::_DeviceCreateCallback"
0x18001294c  movups  xmmword ptr [rsp+0A8h+var_30], xmm0
0x180012951  movups  xmm1, xmmword ptr cs:aCngcnodeDevice+10h; "eCreateCallback"
0x180012958  movups  xmmword ptr [r11-20h], xmm1
0x18001295d  lea     rax, [r11-30h]
0x180012961  mov     [r11-48h], rax
0x180012965  lea     rax, [r11-74h]
0x180012969  mov     [r11-40h], rax
0x18001296d  lea     rax, [r11-78h]
0x180012971  mov     [r11-38h], rax
0x180012975  lea     rcx, [r11-48h]
0x180012979  call    _lambda_f2b522d031acac6736ee111016a9fe68___operator__
0x18001297e  mov     [rsp+0A8h+var_74], 1
0x180012986  lea     rax, [rsp+0A8h+var_48]
0x18001298b  mov     [rsp+0A8h+var_50], rax
0x180012990  mov     [rsp+0A8h+var_58], rdi
0x180012995  lea     rax, [rsp+0A8h+var_58]
0x18001299a  mov     [rsp+0A8h+var_70], rax
0x18001299f  lea     rax, [rsp+0A8h+var_78]
0x1800129a4  mov     [rsp+0A8h+var_68], rax
0x1800129a9  mov     [rsp+0A8h+var_60], 102h
0x1800129b0  cmp     [rsp+0A8h+var_78], esi
0x1800129b4  jge     short loc_180012A01
0x1800129b6  lea     edx, [rsi+2]
0x1800129b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800129be  lea     rax, WPP_GLOBAL_Control
0x1800129c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129cc  cmp     rcx, rax
0x1800129cf  jz      short loc_180012A28
0x1800129d1  test    byte ptr [rcx+1Ch], 1
0x1800129d5  jz      short loc_180012A28
0x1800129d7  cmp     byte ptr [rcx+19h], 2
0x1800129db  jb      short loc_180012A28
0x1800129dd  lea     edx, [rsi+1Eh]
0x1800129e0  mov     eax, [rsp+0A8h+var_78]
0x1800129e4  mov     [rsp+0A8h+var_88], eax
0x1800129e8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800129ef  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x1800129f6  mov     rcx, [rcx+10h]
0x1800129fa  call    WPP_SF_sd
0x1800129ff  jmp     short loc_180012A28
0x180012a01  lea     rcx, [rdi+18h]
0x180012a05  cmp     [rbx], si
0x180012a08  jnz     short loc_180012A0F
0x180012a0a  mov     r8, rsi
0x180012a0d  jmp     short loc_180012A1D
0x180012a0f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012a13  inc     r8
0x180012a16  cmp     [rbx+r8*2], si
0x180012a1b  jnz     short loc_180012A13
0x180012a1d  mov     rdx, rbx
0x180012a20  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180012a25  nop
0x180012a26  jmp     short $+2
0x180012a28  lea     rcx, [rsp+0A8h+var_70]
0x180012a2d  call    wil__details__ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979_____operator__
0x180012a32  nop
0x180012a33  lea     rcx, [rsp+0A8h+var_50]
0x180012a38  call    WppTraceUnwinder__lambda_f2b522d031acac6736ee111016a9fe68_______WppTraceUnwinder__lambda_f2b522d031acac6736ee111016a9fe68____
0x180012a3d  mov     rcx, [rsp+0A8h+var_10]
0x180012a45  xor     rcx, rsp; StackCookie
0x180012a48  call    __security_check_cookie
0x180012a4d  lea     r11, [rsp+0A8h+var_8]
0x180012a55  mov     rbx, [r11+10h]
0x180012a59  mov     rsi, [r11+18h]
0x180012a5d  mov     rsp, r11
0x180012a60  pop     rdi
0x180012a61  retn
```
