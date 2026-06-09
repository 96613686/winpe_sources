# CDownloadService::ModifyJobSource(_GUID const &,ushort const *,ushort const *)

- ea: `0x18001bfcc`
- end: `0x18001c31f`
- name: `?ModifyJobSource@CDownloadService@@QEAAJAEBU_GUID@@PEBG1@Z`
- size: `851`
- prototype: `int(CDownloadService *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013330`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x18000a2c0`
- `0x18000a358`
- `0x18001afb4`
- `0x18001bfcc`
- `0x18001c54c`
- `0x18001e154`
- `0x18001e530`
- `0x18001f420`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18001c04a`
- `ADVAPI32!RevertToSelf` at `0x18001c04a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDownloadService::ModifyJobSource(
        CDownloadService *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char v8; // di
  _QWORD *v9; // r9
  __int64 v10; // rdx
  int BITSJob; // esi
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  _QWORD *v15; // rdi
  wchar_t *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  _QWORD *v19; // rdi
  wchar_t *v20; // rax
  int v21; // eax
  LPCWSTR v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  _BYTE v27[8]; // [rsp+20h] [rbp-99h] BYREF
  struct IBackgroundCopyJob *v28[2]; // [rsp+28h] [rbp-91h] BYREF
  _BYTE v29[32]; // [rsp+38h] [rbp-81h] BYREF
  _WORD v30[8]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v31; // [rsp+68h] [rbp-51h]
  __int64 v32; // [rsp+70h] [rbp-49h]
  _WORD v33[8]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v34; // [rsp+88h] [rbp-31h]
  __int64 v35; // [rsp+90h] [rbp-29h]
  _WORD v36[8]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-11h]
  __int64 v38; // [rsp+B0h] [rbp-9h]
  _BYTE v39[32]; // [rsp+B8h] [rbp-1h] BYREF

  v28[0] = 0;
  v38 = 7;
  v37 = 0;
  v36[0] = 0;
  v35 = 7;
  v34 = 0;
  v33[0] = 0;
  v32 = 7;
  v31 = 0;
  v30[0] = 0;
  v8 = 0;
  v27[0] = 0;
  if ( *((_BYTE *)this + 8) )
  {
    RevertToSelf();
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = (_QWORD *)((char *)this + 16);
      if ( *((_QWORD *)this + 5) >= 8u )
        v9 = (_QWORD *)*v9;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v9);
    }
    v8 = 1;
  }
  BITSJob = FindBITSJob(a2, v28);
  if ( BITSJob < 0
    || (std::wstring::wstring(v29, a4),
        std::wstring::wstring(v39, a3),
        BITSJob = ModifySourceOfBITSFiles(v28[0], v39, v29),
        LOBYTE(v12) = 1,
        std::wstring::_Tidy(v39, v12, 0),
        LOBYTE(v13) = 1,
        std::wstring::_Tidy(v29, v13, 0),
        BITSJob < 0) )
  {
    if ( !v8 )
      goto LABEL_45;
  }
  else
  {
    if ( !v8 )
      goto LABEL_45;
    v14 = *((_DWORD *)this + 12);
    v15 = (_QWORD *)((char *)this + 16);
    v16 = (wchar_t *)std::wstring::wstring(v29, (char *)this + 16);
    v17 = __ImpersonateUser(v16, v14, v27);
    BITSJob = v17;
    if ( v17 >= 0 )
    {
      if ( v27[0] )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v15 = (_QWORD *)*v15;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v15);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          if ( *((_QWORD *)this + 5) >= 8u )
            v15 = (_QWORD *)*v15;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v15);
        }
        BITSJob = -2147418113;
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
        (unsigned int)v17);
    }
  }
  if ( v27[0] )
    goto LABEL_45;
  v18 = *((_DWORD *)this + 12);
  v19 = (_QWORD *)((char *)this + 16);
  v20 = (wchar_t *)std::wstring::wstring(v29, (char *)this + 16);
  v21 = __ImpersonateUser(v20, v18, v27);
  BITSJob = v21;
  if ( v21 >= 0 )
  {
    if ( v27[0] )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_45;
      if ( *((_QWORD *)this + 5) >= 8u )
        v19 = (_QWORD *)*v19;
      v23 = 64;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_45;
      if ( *((_QWORD *)this + 5) >= 8u )
        v19 = (_QWORD *)*v19;
      v23 = 63;
    }
    WPP_SF_S(*((_QWORD *)v22 + 2), v23, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, v19);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
      (unsigned int)v21);
LABEL_45:
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v30, v10, 0);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(v33, v24, 0);
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(v36, v25, 0);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)v28);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001bfcc  push    rbp
0x18001bfce  push    rbx
0x18001bfcf  push    rsi
0x18001bfd0  push    rdi
0x18001bfd1  push    r12
0x18001bfd3  push    r14
0x18001bfd5  push    r15
0x18001bfd7  lea     rbp, [rsp-27h]
0x18001bfdc  sub     rsp, 0E0h
0x18001bfe3  mov     rax, cs:__security_cookie
0x18001bfea  xor     rax, rsp
0x18001bfed  mov     [rbp+57h+var_38], rax
0x18001bff1  mov     r12, r9
0x18001bff4  mov     r15, r8
0x18001bff7  mov     rbx, rdx
0x18001bffa  mov     r14, rcx
0x18001bffd  mov     [rsp+110h+var_E8], 0
0x18001c006  mov     ecx, 7
0x18001c00b  mov     [rbp+57h+var_60], rcx
0x18001c00f  mov     [rbp+57h+var_68], 0
0x18001c017  xor     eax, eax
0x18001c019  mov     [rbp+57h+var_78], ax
0x18001c01d  mov     [rbp+57h+var_80], rcx
0x18001c021  mov     [rbp+57h+var_88], rax
0x18001c025  mov     [rbp+57h+var_98], ax
0x18001c029  mov     [rbp+57h+var_A0], rcx
0x18001c02d  mov     [rbp+57h+var_A8], rax
0x18001c031  mov     [rbp+57h+var_B8], ax
0x18001c035  xor     dil, dil
0x18001c038  mov     [rsp+110h+var_F0], dil
0x18001c03d  lea     rsi, WPP_GLOBAL_Control
0x18001c044  cmp     [r14+8], dil
0x18001c048  jz      short loc_18001C08E
0x18001c04a  call    cs:__imp_RevertToSelf
0x18001c051  nop     dword ptr [rax+rax+00h]
0x18001c056  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c05d  cmp     rcx, rsi
0x18001c060  jz      short loc_18001C08B
0x18001c062  test    byte ptr [rcx+1Ch], 1
0x18001c066  jz      short loc_18001C08B
0x18001c068  lea     r9, [r14+10h]
0x18001c06c  cmp     qword ptr [r9+18h], 8
0x18001c071  jb      short loc_18001C076
0x18001c073  mov     r9, [r9]
0x18001c076  mov     edx, 3Ah ; ':'
0x18001c07b  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c082  mov     rcx, [rcx+10h]
0x18001c086  call    WPP_SF_S
0x18001c08b  mov     dil, 1
0x18001c08e  lea     rdx, [rsp+110h+var_E8]; struct IBackgroundCopyJob **
0x18001c093  mov     rcx, rbx; Uuid
0x18001c096  call    ?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z; FindBITSJob(_GUID const &,IBackgroundCopyJob * *)
0x18001c09b  mov     esi, eax
0x18001c09d  test    eax, eax
0x18001c09f  js      loc_18001C1F7
0x18001c0a5  mov     rdx, r12
0x18001c0a8  lea     rcx, [rsp+110h+var_D8]
0x18001c0ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c0b2  nop
0x18001c0b3  mov     rdx, r15
0x18001c0b6  lea     rcx, [rbp+57h+var_58]
0x18001c0ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c0bf  nop
0x18001c0c0  lea     r8, [rsp+110h+var_D8]
0x18001c0c5  lea     rdx, [rbp+57h+var_58]
0x18001c0c9  mov     rcx, [rsp+110h+var_E8]
0x18001c0ce  call    ?ModifySourceOfBITSFiles@@YAJPEAUIBackgroundCopyJob@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; ModifySourceOfBITSFiles(IBackgroundCopyJob *,std::wstring const &,std::wstring const &)
0x18001c0d3  mov     esi, eax
0x18001c0d5  mov     ebx, eax
0x18001c0d7  shr     ebx, 1Fh
0x18001c0da  xor     r8d, r8d
0x18001c0dd  mov     dl, 1
0x18001c0df  lea     rcx, [rbp+57h+var_58]
0x18001c0e3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c0e8  nop
0x18001c0e9  xor     r8d, r8d
0x18001c0ec  mov     dl, 1
0x18001c0ee  lea     rcx, [rsp+110h+var_D8]
0x18001c0f3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c0f8  test    bl, bl
0x18001c0fa  jnz     loc_18001C1F7
0x18001c100  test    dil, dil
0x18001c103  jz      loc_18001C2C7
0x18001c109  mov     ebx, [r14+30h]
0x18001c10d  lea     rdi, [r14+10h]
0x18001c111  mov     rdx, rdi
0x18001c114  lea     rcx, [rsp+110h+var_D8]
0x18001c119  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c11e  lea     r8, [rsp+110h+var_F0]
0x18001c123  mov     edx, ebx; SessionId
0x18001c125  mov     rcx, rax; String2
0x18001c128  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001c12d  mov     esi, eax
0x18001c12f  test    eax, eax
0x18001c131  jns     short loc_18001C171
0x18001c133  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c13a  lea     r15, WPP_GLOBAL_Control
0x18001c141  cmp     rcx, r15
0x18001c144  jz      loc_18001C207
0x18001c14a  test    byte ptr [rcx+1Ch], 4
0x18001c14e  jz      loc_18001C207
0x18001c154  mov     edx, 3Bh ; ';'
0x18001c159  mov     r9d, eax
0x18001c15c  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c163  mov     rcx, [rcx+10h]
0x18001c167  call    WPP_SF_d
0x18001c16c  jmp     loc_18001C207
0x18001c171  cmp     [rsp+110h+var_F0], 0
0x18001c176  jnz     short loc_18001C1BA
0x18001c178  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c17f  lea     r15, WPP_GLOBAL_Control
0x18001c186  cmp     rcx, r15
0x18001c189  jz      short loc_18001C1B3
0x18001c18b  test    byte ptr [rcx+1Ch], 4
0x18001c18f  jz      short loc_18001C1B3
0x18001c191  cmp     qword ptr [rdi+18h], 8
0x18001c196  jb      short loc_18001C19B
0x18001c198  mov     rdi, [rdi]
0x18001c19b  mov     edx, 3Ch ; '<'
0x18001c1a0  mov     r9, rdi
0x18001c1a3  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c1aa  mov     rcx, [rcx+10h]
0x18001c1ae  call    WPP_SF_S
0x18001c1b3  mov     esi, 8000FFFFh
0x18001c1b8  jmp     short loc_18001C207
0x18001c1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1c1  lea     r15, WPP_GLOBAL_Control
0x18001c1c8  cmp     rcx, r15
0x18001c1cb  jz      short loc_18001C207
0x18001c1cd  test    byte ptr [rcx+1Ch], 1
0x18001c1d1  jz      short loc_18001C207
0x18001c1d3  cmp     qword ptr [rdi+18h], 8
0x18001c1d8  jb      short loc_18001C1DD
0x18001c1da  mov     rdi, [rdi]
0x18001c1dd  mov     edx, 3Dh ; '='
0x18001c1e2  mov     r9, rdi
0x18001c1e5  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c1ec  mov     rcx, [rcx+10h]
0x18001c1f0  call    WPP_SF_S
0x18001c1f5  jmp     short loc_18001C207
0x18001c1f7  test    dil, dil
0x18001c1fa  jz      loc_18001C2C7
0x18001c200  lea     r15, WPP_GLOBAL_Control
0x18001c207  cmp     [rsp+110h+var_F0], 0
0x18001c20c  jnz     loc_18001C2C7
0x18001c212  mov     ebx, [r14+30h]
0x18001c216  lea     rdi, [r14+10h]
0x18001c21a  mov     rdx, rdi
0x18001c21d  lea     rcx, [rsp+110h+var_D8]
0x18001c222  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c227  lea     r8, [rsp+110h+var_F0]
0x18001c22c  mov     edx, ebx; SessionId
0x18001c22e  mov     rcx, rax; String2
0x18001c231  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001c236  mov     esi, eax
0x18001c238  test    eax, eax
0x18001c23a  jns     short loc_18001C268
0x18001c23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c243  cmp     rcx, r15
0x18001c246  jz      short loc_18001C2C7
0x18001c248  test    byte ptr [rcx+1Ch], 4
0x18001c24c  jz      short loc_18001C2C7
0x18001c24e  mov     edx, 3Eh ; '>'
0x18001c253  mov     r9d, eax
0x18001c256  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c25d  mov     rcx, [rcx+10h]
0x18001c261  call    WPP_SF_d
0x18001c266  jmp     short loc_18001C2C7
0x18001c268  cmp     [rsp+110h+var_F0], 0
0x18001c26d  jnz     short loc_18001C292
0x18001c26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c276  cmp     rcx, r15
0x18001c279  jz      short loc_18001C2C7
0x18001c27b  test    byte ptr [rcx+1Ch], 4
0x18001c27f  jz      short loc_18001C2C7
0x18001c281  cmp     qword ptr [rdi+18h], 8
0x18001c286  jb      short loc_18001C28B
0x18001c288  mov     rdi, [rdi]
0x18001c28b  mov     edx, 3Fh ; '?'
0x18001c290  jmp     short loc_18001C2B3
0x18001c292  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c299  cmp     rcx, r15
0x18001c29c  jz      short loc_18001C2C7
0x18001c29e  test    byte ptr [rcx+1Ch], 1
0x18001c2a2  jz      short loc_18001C2C7
0x18001c2a4  cmp     qword ptr [rdi+18h], 8
0x18001c2a9  jb      short loc_18001C2AE
0x18001c2ab  mov     rdi, [rdi]
0x18001c2ae  mov     edx, 40h ; '@'
0x18001c2b3  mov     r9, rdi
0x18001c2b6  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c2bd  mov     rcx, [rcx+10h]
0x18001c2c1  call    WPP_SF_S
0x18001c2c6  nop
0x18001c2c7  xor     r8d, r8d
0x18001c2ca  mov     dl, 1
0x18001c2cc  lea     rcx, [rbp+57h+var_B8]
0x18001c2d0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c2d5  nop
0x18001c2d6  xor     r8d, r8d
0x18001c2d9  mov     dl, 1
0x18001c2db  lea     rcx, [rbp+57h+var_98]
0x18001c2df  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c2e4  nop
0x18001c2e5  xor     r8d, r8d
0x18001c2e8  mov     dl, 1
0x18001c2ea  lea     rcx, [rbp+57h+var_78]
0x18001c2ee  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c2f3  nop
0x18001c2f4  lea     rcx, [rsp+110h+var_E8]
0x18001c2f9  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001c2fe  mov     eax, esi
0x18001c300  mov     rcx, [rbp+57h+var_38]
0x18001c304  xor     rcx, rsp; StackCookie
0x18001c307  call    __security_check_cookie
0x18001c30c  add     rsp, 0E0h
0x18001c313  pop     r15
0x18001c315  pop     r14
0x18001c317  pop     r12
0x18001c319  pop     rdi
0x18001c31a  pop     rsi
0x18001c31b  pop     rbx
0x18001c31c  pop     rbp
0x18001c31d  retn
```
