# BuildPathNames

- ea: `0x18001db8c`
- end: `0x18001de0a`
- name: `BuildPathNames`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d8d0`
- `0x180036698`

## callees

- `0x18000bf84`
- `0x18000c034`
- `0x18000f2b0`
- `0x18001db8c`
- `0x180022340`
- `0x180023548`
- `0x1800249f0`
- `0x1800254b4`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001dc17`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001dc17`

## pseudocode

```c
__int64 __fastcall BuildPathNames(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 result; // rax
  __int128 pExceptionObject; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v13; // [rsp+30h] [rbp-99h]
  unsigned __int64 v14; // [rsp+38h] [rbp-91h]
  int v15; // [rsp+40h] [rbp-89h]
  __int64 v16; // [rsp+48h] [rbp-81h] BYREF
  _WORD v17[72]; // [rsp+50h] [rbp-79h] BYREF

  v16 = a2;
  memset_0(v17, 0, 0x84u);
  tlx::split_path<wchar_t>::split_path<wchar_t>(&pExceptionObject, &v16);
  v7 = v13;
  v8 = (__int64)(v14 - v13) >> 1;
  if ( !v8 || (v9 = (v13 - (__int64)pExceptionObject) >> 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 2);
    }
    v14 = 0xFFFFFFFF00000002uLL;
    v13 = 0;
    v15 = 1234;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  _o__ui64tow_s(a1, v17, 66);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a4,
                           v7,
                           v8) )
    goto LABEL_17;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(a4, 95) )
    goto LABEL_17;
  v10 = -1;
  do
    ++v10;
  while ( v17[v10] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a4,
                           v17,
                           v10) )
  {
LABEL_17:
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    v13 = 0;
    v14 = -4294967282LL;
    pExceptionObject = 0;
    v15 = 1243;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a3,
                           pExceptionObject,
                           v9)
    || (result = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                   a3,
                   L"LocaleMetaData",
                   14),
        !(_BYTE)result) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    v13 = 0;
    v14 = -4294967282LL;
    pExceptionObject = 0;
    v15 = 1251;
    throw (EvtException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18001db8c  push    rbp
0x18001db8e  push    rbx
0x18001db8f  push    rsi
0x18001db90  push    rdi
0x18001db91  push    r12
0x18001db93  push    r14
0x18001db95  push    r15
0x18001db97  lea     rbp, [rsp-27h]
0x18001db9c  sub     rsp, 0F0h
0x18001dba3  mov     rax, cs:__security_cookie
0x18001dbaa  xor     rax, rsp
0x18001dbad  mov     [rbp+57h+var_40], rax
0x18001dbb1  mov     r15, r8
0x18001dbb4  mov     r12d, ecx
0x18001dbb7  mov     [rsp+120h+var_D8], rdx
0x18001dbbc  lea     rcx, [rbp+57h+var_D0]; void *
0x18001dbc0  xor     edx, edx; Val
0x18001dbc2  mov     r8d, 84h; Size
0x18001dbc8  mov     rsi, r9
0x18001dbcb  call    memset_0
0x18001dbd0  lea     rdx, [rsp+120h+var_D8]
0x18001dbd5  lea     rcx, [rsp+120h+pExceptionObject]
0x18001dbda  call    ??$?0PEB_W_W@?$split_path@_W@tlx@@QEAA@AEBQEB_W@Z; tlx::split_path<wchar_t>::split_path<wchar_t>(wchar_t const * const &)
0x18001dbdf  mov     rbx, [rsp+120h+var_F0]
0x18001dbe4  mov     r14, [rsp+120h+var_E8]
0x18001dbe9  sub     r14, rbx
0x18001dbec  sar     r14, 1
0x18001dbef  jz      loc_18001DD7A
0x18001dbf5  mov     rdi, rbx
0x18001dbf8  sub     rdi, qword ptr [rsp+120h+pExceptionObject]
0x18001dbfd  sar     rdi, 1
0x18001dc00  jz      loc_18001DD7A
0x18001dc06  mov     r9d, 0Ah
0x18001dc0c  lea     rdx, [rbp+57h+var_D0]
0x18001dc10  mov     ecx, r12d
0x18001dc13  lea     r8d, [r9+38h]
0x18001dc17  call    cs:__imp__o__ui64tow_s
0x18001dc1d  mov     r8, r14
0x18001dc20  mov     rdx, rbx
0x18001dc23  mov     rcx, rsi
0x18001dc26  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001dc2b  xor     ebx, ebx
0x18001dc2d  test    al, al
0x18001dc2f  jz      loc_18001DD0C
0x18001dc35  lea     edx, [rbx+5Fh]
0x18001dc38  mov     rcx, rsi
0x18001dc3b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18001dc40  test    al, al
0x18001dc42  jz      loc_18001DD0C
0x18001dc48  lea     rax, [rbp+57h+var_D0]
0x18001dc4c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001dc50  inc     r8
0x18001dc53  cmp     [rax+r8*2], bx
0x18001dc58  jnz     short loc_18001DC50
0x18001dc5a  lea     rdx, [rbp+57h+var_D0]
0x18001dc5e  mov     rcx, rsi
0x18001dc61  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001dc66  test    al, al
0x18001dc68  jz      loc_18001DD0C
0x18001dc6e  mov     rdx, qword ptr [rsp+120h+pExceptionObject]
0x18001dc73  mov     r8, rdi
0x18001dc76  mov     rcx, r15
0x18001dc79  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001dc7e  mov     edi, 0Eh
0x18001dc83  test    al, al
0x18001dc85  jz      short loc_18001DCA1
0x18001dc87  mov     r8d, edi
0x18001dc8a  lea     rdx, aLocalemetadata; "LocaleMetaData"
0x18001dc91  mov     rcx, r15
0x18001dc94  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001dc99  test    al, al
0x18001dc9b  jnz     loc_18001DDEC
0x18001dca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dca8  lea     rax, WPP_GLOBAL_Control
0x18001dcaf  cmp     rcx, rax
0x18001dcb2  jz      short loc_18001DCD8
0x18001dcb4  test    byte ptr [rcx+1Ch], 1
0x18001dcb8  jz      short loc_18001DCD8
0x18001dcba  cmp     byte ptr [rcx+19h], 2
0x18001dcbe  jb      short loc_18001DCD8
0x18001dcc0  mov     rcx, [rcx+10h]
0x18001dcc4  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18001dccb  mov     edx, 35h ; '5'
0x18001dcd0  mov     r9d, edi
0x18001dcd3  call    WPP_SF_D
0x18001dcd8  xorps   xmm0, xmm0
0x18001dcdb  mov     [rsp+120h+var_F0], rbx
0x18001dce0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001dce7  mov     dword ptr [rsp+120h+var_E8], edi
0x18001dceb  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001dcf0  mov     dword ptr [rsp+120h+var_E8+4], 0FFFFFFFFh
0x18001dcf8  movdqu  [rsp+120h+pExceptionObject], xmm0
0x18001dcfe  mov     [rsp+120h+var_E0], 4E3h
0x18001dd06  call    _CxxThrowException_0
0x18001dd0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd13  lea     rax, WPP_GLOBAL_Control
0x18001dd1a  mov     edi, 0Eh
0x18001dd1f  cmp     rcx, rax
0x18001dd22  jz      short loc_18001DD46
0x18001dd24  test    byte ptr [rcx+1Ch], 1
0x18001dd28  jz      short loc_18001DD46
0x18001dd2a  cmp     byte ptr [rcx+19h], 2
0x18001dd2e  jb      short loc_18001DD46
0x18001dd30  mov     rcx, [rcx+10h]
0x18001dd34  lea     edx, [rdi+26h]
0x18001dd37  mov     r9d, edi
0x18001dd3a  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18001dd41  call    WPP_SF_D
0x18001dd46  xorps   xmm0, xmm0
0x18001dd49  mov     [rsp+120h+var_F0], rbx
0x18001dd4e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001dd55  mov     dword ptr [rsp+120h+var_E8], edi
0x18001dd59  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001dd5e  mov     dword ptr [rsp+120h+var_E8+4], 0FFFFFFFFh
0x18001dd66  movdqu  [rsp+120h+pExceptionObject], xmm0
0x18001dd6c  mov     [rsp+120h+var_E0], 4DBh
0x18001dd74  call    _CxxThrowException_0
0x18001dd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd81  lea     rax, WPP_GLOBAL_Control
0x18001dd88  cmp     rcx, rax
0x18001dd8b  jz      short loc_18001DDB2
0x18001dd8d  test    byte ptr [rcx+1Ch], 1
0x18001dd91  jz      short loc_18001DDB2
0x18001dd93  cmp     byte ptr [rcx+19h], 2
0x18001dd97  jb      short loc_18001DDB2
0x18001dd99  mov     rcx, [rcx+10h]
0x18001dd9d  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18001dda4  mov     edx, 33h ; '3'
0x18001dda9  lea     r9d, [rdx-31h]
0x18001ddad  call    WPP_SF_D
0x18001ddb2  xorps   xmm0, xmm0
0x18001ddb5  mov     dword ptr [rsp+120h+var_E8], 2
0x18001ddbd  xor     ebx, ebx
0x18001ddbf  mov     dword ptr [rsp+120h+var_E8+4], 0FFFFFFFFh
0x18001ddc7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001ddce  mov     [rsp+120h+var_F0], rbx
0x18001ddd3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001ddd8  mov     [rsp+120h+var_E0], 4D2h
0x18001dde0  movdqu  [rsp+120h+pExceptionObject], xmm0
0x18001dde6  call    _CxxThrowException_0
0x18001ddec  mov     rcx, [rbp+57h+var_40]
0x18001ddf0  xor     rcx, rsp; StackCookie
0x18001ddf3  call    __security_check_cookie
0x18001ddf8  add     rsp, 0F0h
0x18001ddff  pop     r15
0x18001de01  pop     r14
0x18001de03  pop     r12
0x18001de05  pop     rdi
0x18001de06  pop     rsi
0x18001de07  pop     rbx
0x18001de08  pop     rbp
0x18001de09  retn
```
