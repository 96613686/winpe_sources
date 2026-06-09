# CBusNode::_CreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180009490`
- end: `0x180009680`
- name: `?_CreateCallback@CBusNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `496`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, _QWORD *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180006d40`
- `0x1800084a0`
- `0x18000887c`
- `0x180008a70`
- `0x180008ab0`
- `0x180009490`
- `0x1800096f4`
- `0x180009970`
- `0x180009b0c`
- `0x180009c38`
- `0x18001e020`

## string_xrefs

- `0x1800094c4`: `CBusNode::_CreateCallback`

## pseudocode

```c
void __fastcall CBusNode::_CreateCallback(struct HSWDEVICE__ *a1, int a2, _QWORD *a3, const unsigned __int16 *a4)
{
  CBusNode *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  int v10; // [rsp+30h] [rbp-A8h] BYREF
  int v11; // [rsp+34h] [rbp-A4h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-A0h] BYREF
  const unsigned __int16 *v13; // [rsp+40h] [rbp-98h] BYREF
  _QWORD *v14; // [rsp+48h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-88h] BYREF
  __int16 v16; // [rsp+60h] [rbp-78h]
  _QWORD v17[2]; // [rsp+68h] [rbp-70h] BYREF
  __int16 v18; // [rsp+78h] [rbp-60h]
  _QWORD v19[3]; // [rsp+80h] [rbp-58h] BYREF
  char v20[32]; // [rsp+98h] [rbp-40h] BYREF

  v13 = a4;
  v10 = a2;
  v11 = 0;
  strcpy(v20, "CBusNode::_CreateCallback");
  v19[0] = v20;
  v19[1] = &v11;
  v19[2] = &v10;
  lambda_78e6e0b57a5de3623253bc47ed718445_::operator()(v19);
  v11 = 1;
  v12 = v19;
  v14 = a3;
  v17[0] = &v14;
  v17[1] = &v10;
  v18 = 258;
  v15[0] = &v13;
  v15[1] = &v10;
  v16 = 256;
  if ( v10 >= 0 )
  {
    v10 = CBusNode::_InitializeBusNode(v6, a1);
    if ( v10 >= 0 )
    {
      if ( *v13 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v13[v7] );
      }
      else
      {
        v7 = 0;
      }
      try
      {
        std::wstring::assign((_QWORD *)(v14[2] + 16LL), (unsigned __int64)v13, v7);
        if ( (Microsoft_Windows_SmartCard_DeviceEnumEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)SCDEVICEENUM_CREATE, v13, 0);
        WppTraceIndent(v8, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v9 = (_QWORD *)(v14[2] + 16LL);
          if ( *(_QWORD *)(v14[2] + 40LL) >= 8u )
            v9 = (_QWORD *)*v9;
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (int)&WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids,
            (int)WPP_pszIndent,
            (__int64)v9);
        }
        HIBYTE(v16) = 0;
      }
      catch ( std::bad_alloc )
      {
        v10 = -2147024882;
      }
    }
  }
  wil::details::ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563___::operator()(v15);
  wil::details::ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9___::operator()(v17);
  WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445____::_WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445____(&v12);
}

```

## disassembly

```asm
0x180009490  mov     r11, rsp
0x180009493  push    rbx
0x180009494  push    rsi
0x180009495  push    rdi
0x180009496  sub     rsp, 0C0h
0x18000949d  mov     rax, cs:__security_cookie
0x1800094a4  xor     rax, rsp
0x1800094a7  mov     [rsp+0D8h+var_20], rax
0x1800094af  mov     rbx, r8
0x1800094b2  mov     rdi, rcx
0x1800094b5  mov     [rsp+0D8h+var_98], r9
0x1800094ba  mov     [rsp+0D8h+var_A8], edx
0x1800094be  xor     esi, esi
0x1800094c0  mov     [rsp+0D8h+var_A4], esi
0x1800094c4  movups  xmm0, xmmword ptr cs:aCbusnodeCreate; "CBusNode::_CreateCallback"
0x1800094cb  movups  xmmword ptr [r11-40h], xmm0
0x1800094d0  movups  xmm1, xmmword ptr cs:aCbusnodeCreate+0Ah; "_CreateCallback"
0x1800094d7  movups  xmmword ptr [r11-36h], xmm1
0x1800094dc  lea     rax, [r11-40h]
0x1800094e0  mov     [r11-58h], rax
0x1800094e4  lea     rax, [rsp+0D8h+var_A4]
0x1800094e9  mov     [r11-50h], rax
0x1800094ed  lea     rax, [rsp+0D8h+var_A8]
0x1800094f2  mov     [r11-48h], rax
0x1800094f6  lea     rcx, [r11-58h]
0x1800094fa  call    _lambda_78e6e0b57a5de3623253bc47ed718445___operator__
0x1800094ff  mov     [rsp+0D8h+var_A4], 1
0x180009507  lea     rax, [rsp+0D8h+var_58]
0x18000950f  mov     [rsp+0D8h+var_A0], rax
0x180009514  mov     [rsp+0D8h+var_90], rbx
0x180009519  lea     rax, [rsp+0D8h+var_90]
0x18000951e  mov     [rsp+0D8h+var_70], rax
0x180009523  lea     rax, [rsp+0D8h+var_A8]
0x180009528  mov     [rsp+0D8h+var_68], rax
0x18000952d  mov     [rsp+0D8h+var_60], 102h
0x180009534  lea     rax, [rsp+0D8h+var_98]
0x180009539  mov     [rsp+0D8h+var_88], rax
0x18000953e  lea     rax, [rsp+0D8h+var_A8]
0x180009543  mov     [rsp+0D8h+var_80], rax
0x180009548  mov     [rsp+0D8h+var_78], 100h
0x18000954f  cmp     [rsp+0D8h+var_A8], esi
0x180009553  jl      loc_180009645
0x180009559  mov     rdx, rdi; struct HSWDEVICE__ *
0x18000955c  call    ?_InitializeBusNode@CBusNode@@AEAAJPEAUHSWDEVICE__@@@Z; CBusNode::_InitializeBusNode(HSWDEVICE__ *)
0x180009561  mov     [rsp+0D8h+var_A8], eax
0x180009565  test    eax, eax
0x180009567  jns     short loc_18000958E
0x180009569  lea     rcx, [rsp+0D8h+var_88]
0x18000956e  call    wil__details__ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563_____operator__
0x180009573  nop
0x180009574  lea     rcx, [rsp+0D8h+var_70]
0x180009579  call    wil__details__ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9_____operator__
0x18000957e  nop
0x18000957f  lea     rcx, [rsp+0D8h+var_A0]
0x180009584  call    WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445_______WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445____
0x180009589  jmp     loc_180009665
0x18000958e  mov     rdx, [rsp+0D8h+var_98]
0x180009593  mov     rax, [rsp+0D8h+var_90]
0x180009598  mov     rcx, [rax+10h]
0x18000959c  add     rcx, 10h
0x1800095a0  cmp     [rdx], si
0x1800095a3  jnz     short loc_1800095AA
0x1800095a5  mov     r8, rsi
0x1800095a8  jmp     short loc_1800095B8
0x1800095aa  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800095ae  inc     r8
0x1800095b1  cmp     [rdx+r8*2], si
0x1800095b6  jnz     short loc_1800095AE
0x1800095b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800095bd  nop
0x1800095be  test    cs:Microsoft_Windows_SmartCard_DeviceEnumEnableBits, 2
0x1800095c5  jz      short loc_1800095DB
0x1800095c7  xor     r9d, r9d
0x1800095ca  mov     r8, [rsp+0D8h+var_98]
0x1800095cf  lea     rdx, SCDEVICEENUM_CREATE
0x1800095d6  call    McTemplateU0zq_EventWriteTransfer
0x1800095db  mov     edx, 2
0x1800095e0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800095e5  lea     rax, WPP_GLOBAL_Control
0x1800095ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800095f3  cmp     r10, rax
0x1800095f6  jz      short loc_18000963E
0x1800095f8  test    byte ptr [r10+1Ch], 1
0x1800095fd  jz      short loc_18000963E
0x1800095ff  cmp     byte ptr [r10+19h], 4
0x180009604  jb      short loc_18000963E
0x180009606  mov     rax, [rsp+0D8h+var_90]
0x18000960b  mov     rcx, [rax+10h]
0x18000960f  add     rcx, 10h
0x180009613  cmp     qword ptr [rcx+18h], 8
0x180009618  jb      short loc_18000961D
0x18000961a  mov     rcx, [rcx]
0x18000961d  mov     edx, 17h
0x180009622  mov     [rsp+0D8h+var_B8], rcx
0x180009627  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000962e  lea     r8, WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids
0x180009635  mov     rcx, [r10+10h]
0x180009639  call    WPP_SF_sS
0x18000963e  mov     byte ptr [rsp+0D8h+var_78+1], sil
0x180009643  jmp     short $+2
0x180009645  lea     rcx, [rsp+0D8h+var_88]
0x18000964a  call    wil__details__ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563_____operator__
0x18000964f  nop
0x180009650  lea     rcx, [rsp+0D8h+var_70]
0x180009655  call    wil__details__ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9_____operator__
0x18000965a  nop
0x18000965b  lea     rcx, [rsp+0D8h+var_A0]
0x180009660  call    WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445_______WppTraceUnwinder__lambda_78e6e0b57a5de3623253bc47ed718445____
0x180009665  mov     rcx, [rsp+0D8h+var_20]
0x18000966d  xor     rcx, rsp; StackCookie
0x180009670  call    __security_check_cookie
0x180009675  add     rsp, 0C0h
0x18000967c  pop     rdi
0x18000967d  pop     rsi
0x18000967e  pop     rbx
0x18000967f  retn
```
