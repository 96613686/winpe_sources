# CInformationNode::_CreateCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x180010dd0`
- end: `0x180010fea`
- name: `?_CreateCallback@CInformationNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `538`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, CInformationNode *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001444`
- `0x180006d40`
- `0x180008ab0`
- `0x180009b0c`
- `0x180009c38`
- `0x18000c58c`
- `0x18000db20`
- `0x1800100c4`
- `0x18001041c`
- `0x180010720`
- `0x180010dd0`
- `0x180010ff0`
- `0x1800118c0`
- `0x18001e020`

## string_xrefs

- `0x180010e08`: `CInformationNode::_CreateCallback`

## pseudocode

```c
void __fastcall CInformationNode::_CreateCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        CInformationNode *a3,
        const unsigned __int16 *a4)
{
  void *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r8
  int v10; // [rsp+30h] [rbp-A8h] BYREF
  int v11; // [rsp+34h] [rbp-A4h] BYREF
  CInformationNode *v12; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-98h] BYREF
  const unsigned __int16 *v14; // [rsp+48h] [rbp-90h] BYREF
  CInformationNode **v15; // [rsp+50h] [rbp-88h] BYREF
  __int16 v16; // [rsp+58h] [rbp-80h]
  _QWORD v17[2]; // [rsp+60h] [rbp-78h] BYREF
  __int16 v18; // [rsp+70h] [rbp-68h]
  _QWORD *v19; // [rsp+78h] [rbp-60h] BYREF
  _QWORD v20[4]; // [rsp+80h] [rbp-58h] BYREF
  char v21[40]; // [rsp+A0h] [rbp-38h] BYREF

  v14 = a4;
  v10 = a2;
  v11 = 0;
  strcpy(v21, "CInformationNode::_CreateCallback");
  v20[0] = v21;
  v20[1] = &v11;
  v20[2] = &v10;
  lambda_7106be8a91148646d53201c01d37964c_::operator()(v20);
  v11 = 1;
  v19 = v20;
  v12 = a3;
  v15 = &v12;
  v16 = 258;
  v17[0] = &v14;
  v17[1] = &v10;
  v18 = 256;
  if ( v10 >= 0 )
  {
    try
    {
      v6 = operator new(0x20u);
      v20[3] = v6;
      if ( v6 )
        v7 = std::wstring::wstring(v6, v14);
      else
        v7 = 0;
      v13 = v7;
      if ( (__int64 *)((char *)v12 + 40) != &v13 )
      {
        v13 = 0;
        std::unique_ptr<std::wstring>::reset((__int64 *)v12 + 5, v7);
      }
      ((void (__fastcall *)(__int64 *))std::unique_ptr<std::wstring>::_Delete)(&v13);
      v10 = CInformationNode::_RegisterInterface(v12, a1);
      if ( v10 >= 0 )
      {
        if ( (Microsoft_Windows_SmartCard_DeviceEnumEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v8,
            (const EVENT_DESCRIPTOR *)SCDEVICEENUM_CREATE,
            v14,
            *((_DWORD *)v12 + 13));
        WppTraceIndent(v8, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v9 = (__int64 *)*((_QWORD *)v12 + 5);
          if ( (unsigned __int64)v9[3] < 8 )
            v9 = (__int64 *)((char *)v12 + 40);
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
            (int)WPP_pszIndent,
            *v9);
        }
        HIBYTE(v18) = 0;
        v10 = 0;
      }
    }
    catch ( std::bad_alloc )
    {
      v10 = -2147024882;
    }
  }
  wil::details::ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563___::operator()(v17);
  wil::details::ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366___::operator()(&v15);
  WppTraceUnwinder__lambda_7106be8a91148646d53201c01d37964c____::_WppTraceUnwinder__lambda_7106be8a91148646d53201c01d37964c____(&v19);
}

```

## disassembly

```asm
0x180010dd0  mov     r11, rsp
0x180010dd3  mov     [r11+10h], rbx
0x180010dd7  push    rdi
0x180010dd8  sub     rsp, 0D0h
0x180010ddf  mov     rax, cs:__security_cookie
0x180010de6  xor     rax, rsp
0x180010de9  mov     [rsp+0D8h+var_10], rax
0x180010df1  mov     rbx, r8
0x180010df4  mov     rdi, rcx
0x180010df7  mov     [rsp+0D8h+var_90], r9
0x180010dfc  mov     [rsp+0D8h+var_A8], edx
0x180010e00  mov     [rsp+0D8h+var_A4], 0
0x180010e08  movups  xmm0, xmmword ptr cs:aCinformationno_4; "CInformationNode::_CreateCallback"
0x180010e0f  movups  xmmword ptr [r11-38h], xmm0
0x180010e14  movups  xmm1, xmmword ptr cs:aCinformationno_4+10h; "::_CreateCallback"
0x180010e1b  movups  xmmword ptr [r11-28h], xmm1
0x180010e20  movzx   eax, word ptr cs:aCinformationno_4+20h; "k"
0x180010e27  mov     [r11-18h], ax
0x180010e2c  lea     rax, [r11-38h]
0x180010e30  mov     [r11-58h], rax
0x180010e34  lea     rax, [rsp+0D8h+var_A4]
0x180010e39  mov     [r11-50h], rax
0x180010e3d  lea     rax, [rsp+0D8h+var_A8]
0x180010e42  mov     [r11-48h], rax
0x180010e46  lea     rcx, [r11-58h]
0x180010e4a  call    _lambda_7106be8a91148646d53201c01d37964c___operator__
0x180010e4f  mov     [rsp+0D8h+var_A4], 1
0x180010e57  lea     rax, [rsp+0D8h+var_58]
0x180010e5f  mov     [rsp+0D8h+var_60], rax
0x180010e64  mov     [rsp+0D8h+var_A0], rbx
0x180010e69  lea     rax, [rsp+0D8h+var_A0]
0x180010e6e  mov     [rsp+0D8h+var_88], rax
0x180010e73  mov     [rsp+0D8h+var_80], 102h
0x180010e7a  lea     rax, [rsp+0D8h+var_90]
0x180010e7f  mov     [rsp+0D8h+var_78], rax
0x180010e84  lea     rax, [rsp+0D8h+var_A8]
0x180010e89  mov     [rsp+0D8h+var_70], rax
0x180010e8e  mov     [rsp+0D8h+var_68], 100h
0x180010e95  cmp     [rsp+0D8h+var_A8], 0
0x180010e9a  jl      loc_180010FA9
0x180010ea0  mov     ecx, 20h ; ' '; Size
0x180010ea5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010eaa  mov     [rsp+0D8h+var_40], rax
0x180010eb2  test    rax, rax
0x180010eb5  jz      short loc_180010EC9
0x180010eb7  mov     rdx, [rsp+0D8h+var_90]
0x180010ebc  mov     rcx, rax
0x180010ebf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180010ec4  mov     rdx, rax
0x180010ec7  jmp     short loc_180010ECB
0x180010ec9  xor     edx, edx
0x180010ecb  mov     [rsp+0D8h+var_98], rdx
0x180010ed0  mov     rcx, [rsp+0D8h+var_A0]
0x180010ed5  add     rcx, 28h ; '('
0x180010ed9  lea     rax, [rsp+0D8h+var_98]
0x180010ede  cmp     rcx, rax
0x180010ee1  jz      short loc_180010EF1
0x180010ee3  mov     [rsp+0D8h+var_98], 0
0x180010eec  call    ?reset@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unique_ptr<std::wstring>::reset(std::wstring *)
0x180010ef1  lea     rcx, [rsp+0D8h+var_98]
0x180010ef6  call    ?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::wstring>::_Delete(void)
0x180010efb  nop
0x180010efc  mov     rdx, rdi; struct HSWDEVICE__ *
0x180010eff  mov     rcx, [rsp+0D8h+var_A0]; this
0x180010f04  call    ?_RegisterInterface@CInformationNode@@AEAAJPEAUHSWDEVICE__@@@Z; CInformationNode::_RegisterInterface(HSWDEVICE__ *)
0x180010f09  mov     [rsp+0D8h+var_A8], eax
0x180010f0d  test    eax, eax
0x180010f0f  js      loc_180010FA9
0x180010f15  test    cs:Microsoft_Windows_SmartCard_DeviceEnumEnableBits, 2
0x180010f1c  jz      short loc_180010F38
0x180010f1e  mov     r9, [rsp+0D8h+var_A0]
0x180010f23  mov     r9d, [r9+34h]
0x180010f27  mov     r8, [rsp+0D8h+var_90]
0x180010f2c  lea     rdx, SCDEVICEENUM_CREATE
0x180010f33  call    McTemplateU0zq_EventWriteTransfer
0x180010f38  mov     edx, 2
0x180010f3d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010f42  lea     rax, WPP_GLOBAL_Control
0x180010f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f50  cmp     rcx, rax
0x180010f53  jz      short loc_180010F9A
0x180010f55  test    byte ptr [rcx+1Ch], 1
0x180010f59  jz      short loc_180010F9A
0x180010f5b  cmp     byte ptr [rcx+19h], 4
0x180010f5f  jb      short loc_180010F9A
0x180010f61  mov     rax, [rsp+0D8h+var_A0]
0x180010f66  add     rax, 28h ; '('
0x180010f6a  mov     r8, [rax]
0x180010f6d  cmp     qword ptr [r8+18h], 8
0x180010f72  cmovb   r8, rax
0x180010f76  mov     edx, 17h
0x180010f7b  mov     rax, [r8]
0x180010f7e  mov     [rsp+0D8h+var_B8], rax
0x180010f83  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180010f8a  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x180010f91  mov     rcx, [rcx+10h]
0x180010f95  call    WPP_SF_sS
0x180010f9a  mov     byte ptr [rsp+0D8h+var_68+1], 0
0x180010f9f  mov     [rsp+0D8h+var_A8], 0
0x180010fa7  jmp     short $+2
0x180010fa9  lea     rcx, [rsp+0D8h+var_78]
0x180010fae  call    wil__details__ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563_____operator__
0x180010fb3  nop
0x180010fb4  lea     rcx, [rsp+0D8h+var_88]
0x180010fb9  call    wil__details__ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366_____operator__
0x180010fbe  nop
0x180010fbf  lea     rcx, [rsp+0D8h+var_60]
0x180010fc4  call    WppTraceUnwinder__lambda_7106be8a91148646d53201c01d37964c_______WppTraceUnwinder__lambda_7106be8a91148646d53201c01d37964c____
0x180010fc9  mov     rcx, [rsp+0D8h+var_10]
0x180010fd1  xor     rcx, rsp; StackCookie
0x180010fd4  call    __security_check_cookie
0x180010fd9  mov     rbx, [rsp+0D8h+arg_8]
0x180010fe1  add     rsp, 0D0h
0x180010fe8  pop     rdi
0x180010fe9  retn
```
