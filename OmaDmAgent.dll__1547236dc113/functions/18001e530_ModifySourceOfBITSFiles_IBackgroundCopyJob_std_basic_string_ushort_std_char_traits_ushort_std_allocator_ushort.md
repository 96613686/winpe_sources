# ModifySourceOfBITSFiles(IBackgroundCopyJob *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001e530`
- end: `0x18001e842`
- name: `?ModifySourceOfBITSFiles@@YAJPEAUIBackgroundCopyJob@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `786`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001bfcc`
- `0x18001cb10`

## callees

- `0x1800062ac`
- `0x18000a290`
- `0x18000a358`
- `0x18001afb4`
- `0x18001e530`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e601`
- `msvcrt!_wcsicmp` at `0x18001e601`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ModifySourceOfBITSFiles(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rcx
  LPCWSTR v9; // rcx
  _QWORD *v10; // r9
  _QWORD *v11; // r9
  _QWORD *v12; // rdx
  int v13; // edi
  LPCWSTR v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v18; // [rsp+28h] [rbp-41h] BYREF
  __int64 v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+38h] [rbp-31h] BYREF
  void **v21; // [rsp+40h] [rbp-29h]
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  _WORD v23[8]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  _WORD v26[8]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v27; // [rsp+80h] [rbp+17h]
  __int64 v28; // [rsp+88h] [rbp+1Fh]

  v4 = a2;
  v20 = 0;
  v19 = 0;
  v22 = 0;
  v21 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  v28 = 7;
  v27 = 0;
  v26[0] = 0;
  v25 = 7;
  v24 = 0;
  v23[0] = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids);
  if ( a1 )
  {
    v7 = a3[3] < 8u ? (const wchar_t *)a3 : (const wchar_t *)*a3;
    v8 = v4[3] < 8u ? (const wchar_t *)v4 : (const wchar_t *)*v4;
    if ( _wcsicmp(v8, v7) )
    {
      v18 = 0;
      if ( (**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
             a1,
             &GUID_443c8934_90ff_48ed_bcde_26f5c7450042,
             &v18) )
      {
        v6 = 0;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids);
        goto LABEL_56;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( v4[3] < 8u )
            v10 = v4;
          else
            v10 = (_QWORD *)*v4;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids, v10);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (LPCWSTR)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
        {
          if ( a3[3] < 8u )
            v11 = a3;
          else
            v11 = (_QWORD *)*a3;
          WPP_SF_S(*((_QWORD *)v9 + 2), 13, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids, v11);
        }
      }
      if ( a3[3] >= 8u )
        a3 = (_QWORD *)*a3;
      if ( v4[3] < 8u )
        v12 = v4;
      else
        v12 = (_QWORD *)*v4;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)v18 + 344LL))(v18, v12, a3);
      if ( v13 == 1 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( v4[3] >= 8u )
            v4 = (_QWORD *)*v4;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids, v4);
          v14 = WPP_GLOBAL_Control;
        }
        v6 = v13;
        goto LABEL_49;
      }
      if ( v13 == -2147467263 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_43;
        v15 = 15;
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( v13 != -2147024809
          || WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
          v6 = v13;
          if ( v13 >= 0 )
          {
LABEL_49:
            if ( v14 != (LPCWSTR)&WPP_GLOBAL_Control && (v14[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)v14 + 2), 17, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
          }
LABEL_56:
          ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v18);
          goto LABEL_57;
        }
        v15 = 16;
      }
      WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids);
LABEL_43:
      v6 = v13;
      goto LABEL_56;
    }
  }
  v6 = -2147024809;
LABEL_57:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v23, a2, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v26, v16, 0);
  v21 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v22);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v19);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v20);
  return v6;
}

```

## disassembly

```asm
0x18001e530  mov     [rsp-8+arg_18], rbx
0x18001e535  push    rbp
0x18001e536  push    rsi
0x18001e537  push    rdi
0x18001e538  push    r12
0x18001e53a  push    r13
0x18001e53c  lea     rbp, [rsp-37h]
0x18001e541  sub     rsp, 0A0h
0x18001e548  mov     rax, cs:__security_cookie
0x18001e54f  xor     rax, rsp
0x18001e552  mov     [rbp+57h+var_30], rax
0x18001e556  mov     rdi, r8
0x18001e559  mov     rbx, rdx
0x18001e55c  mov     rsi, rcx
0x18001e55f  mov     [rbp+57h+var_88], 0
0x18001e567  mov     [rbp+57h+var_90], 0
0x18001e56f  mov     [rbp+57h+var_78], 0
0x18001e577  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e57e  mov     [rbp+57h+var_80], rax
0x18001e582  mov     ecx, 7
0x18001e587  mov     [rbp+57h+var_38], rcx
0x18001e58b  mov     [rbp+57h+var_40], 0
0x18001e593  xor     eax, eax
0x18001e595  mov     [rbp+57h+var_50], ax
0x18001e599  mov     [rbp+57h+var_58], rcx
0x18001e59d  mov     [rbp+57h+var_60], rax
0x18001e5a1  mov     [rbp+57h+var_70], ax
0x18001e5a5  lea     r12, WPP_GLOBAL_Control
0x18001e5ac  lea     r13, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids
0x18001e5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5ba  cmp     rcx, r12
0x18001e5bd  jz      short loc_18001E5D4
0x18001e5bf  test    byte ptr [rcx+1Ch], 1
0x18001e5c3  jz      short loc_18001E5D4
0x18001e5c5  lea     edx, [rax+0Bh]
0x18001e5c8  mov     r8, r13
0x18001e5cb  mov     rcx, [rcx+10h]
0x18001e5cf  call    WPP_SF_
0x18001e5d4  test    rsi, rsi
0x18001e5d7  jnz     short loc_18001E5E3
0x18001e5d9  mov     ebx, 80070057h
0x18001e5de  jmp     loc_18001E7D6
0x18001e5e3  cmp     qword ptr [rdi+18h], 8
0x18001e5e8  jb      short loc_18001E5EF
0x18001e5ea  mov     rdx, [rdi]
0x18001e5ed  jmp     short loc_18001E5F2
0x18001e5ef  mov     rdx, rdi; String2
0x18001e5f2  cmp     qword ptr [rbx+18h], 8
0x18001e5f7  jb      short loc_18001E5FE
0x18001e5f9  mov     rcx, [rbx]
0x18001e5fc  jmp     short loc_18001E601
0x18001e5fe  mov     rcx, rbx; String1
0x18001e601  call    cs:__imp__wcsicmp
0x18001e608  nop     dword ptr [rax+rax+00h]
0x18001e60d  test    eax, eax
0x18001e60f  jz      short loc_18001E5D9
0x18001e611  mov     [rbp+57h+var_98], 0
0x18001e619  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e620  mov     [rbp+57h+var_A0], rax
0x18001e624  mov     rax, [rsi]
0x18001e627  lea     r8, [rbp+57h+var_98]
0x18001e62b  lea     rdx, _GUID_443c8934_90ff_48ed_bcde_26f5c7450042
0x18001e632  mov     rcx, rsi
0x18001e635  mov     rax, [rax]
0x18001e638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e63d  test    eax, eax
0x18001e63f  jnz     loc_18001E79D
0x18001e645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e64c  cmp     rcx, r12
0x18001e64f  jz      short loc_18001E6A9
0x18001e651  test    byte ptr [rcx+1Ch], 1
0x18001e655  jz      short loc_18001E67E
0x18001e657  cmp     qword ptr [rbx+18h], 8
0x18001e65c  jb      short loc_18001E663
0x18001e65e  mov     r9, [rbx]
0x18001e661  jmp     short loc_18001E666
0x18001e663  mov     r9, rbx
0x18001e666  mov     edx, 0Ch
0x18001e66b  mov     r8, r13
0x18001e66e  mov     rcx, [rcx+10h]
0x18001e672  call    WPP_SF_S
0x18001e677  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e67e  cmp     rcx, r12
0x18001e681  jz      short loc_18001E6A9
0x18001e683  test    byte ptr [rcx+1Ch], 1
0x18001e687  jz      short loc_18001E6A9
0x18001e689  cmp     qword ptr [rdi+18h], 8
0x18001e68e  jb      short loc_18001E695
0x18001e690  mov     r9, [rdi]
0x18001e693  jmp     short loc_18001E698
0x18001e695  mov     r9, rdi
0x18001e698  mov     edx, 0Dh
0x18001e69d  mov     r8, r13
0x18001e6a0  mov     rcx, [rcx+10h]
0x18001e6a4  call    WPP_SF_S
0x18001e6a9  mov     rcx, [rbp+57h+var_98]
0x18001e6ad  mov     rax, [rcx]
0x18001e6b0  cmp     qword ptr [rdi+18h], 8
0x18001e6b5  jb      short loc_18001E6BA
0x18001e6b7  mov     rdi, [rdi]
0x18001e6ba  cmp     qword ptr [rbx+18h], 8
0x18001e6bf  jb      short loc_18001E6C6
0x18001e6c1  mov     rdx, [rbx]
0x18001e6c4  jmp     short loc_18001E6C9
0x18001e6c6  mov     rdx, rbx
0x18001e6c9  mov     r8, rdi
0x18001e6cc  mov     rax, [rax+158h]
0x18001e6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d8  mov     edi, eax
0x18001e6da  cmp     eax, 1
0x18001e6dd  jnz     short loc_18001E719
0x18001e6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6e6  cmp     rcx, r12
0x18001e6e9  jz      short loc_18001E715
0x18001e6eb  test    [rcx+1Ch], al
0x18001e6ee  jz      short loc_18001E715
0x18001e6f0  cmp     qword ptr [rbx+18h], 8
0x18001e6f5  jb      short loc_18001E6FA
0x18001e6f7  mov     rbx, [rbx]
0x18001e6fa  mov     edx, 0Eh
0x18001e6ff  mov     r9, rbx
0x18001e702  mov     r8, r13
0x18001e705  mov     rcx, [rcx+10h]
0x18001e709  call    WPP_SF_S
0x18001e70e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e715  mov     ebx, edi
0x18001e717  jmp     short loc_18001E770
0x18001e719  cmp     edi, 80004001h
0x18001e71f  jnz     short loc_18001E748
0x18001e721  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e728  cmp     rcx, r12
0x18001e72b  jz      short loc_18001E744
0x18001e72d  test    byte ptr [rcx+1Ch], 1
0x18001e731  jz      short loc_18001E744
0x18001e733  mov     edx, 0Fh
0x18001e738  mov     r8, r13
0x18001e73b  mov     rcx, [rcx+10h]
0x18001e73f  call    WPP_SF_
0x18001e744  mov     ebx, edi
0x18001e746  jmp     short loc_18001E7C1
0x18001e748  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e74f  mov     ebx, 80070057h
0x18001e754  cmp     edi, ebx
0x18001e756  jnz     short loc_18001E76A
0x18001e758  cmp     rcx, r12
0x18001e75b  jz      short loc_18001E76A
0x18001e75d  test    byte ptr [rcx+1Ch], 1
0x18001e761  jz      short loc_18001E76A
0x18001e763  mov     edx, 10h
0x18001e768  jmp     short loc_18001E738
0x18001e76a  mov     ebx, edi
0x18001e76c  test    edi, edi
0x18001e76e  js      short loc_18001E7C1
0x18001e770  cmp     rcx, r12
0x18001e773  jz      short loc_18001E78C
0x18001e775  test    byte ptr [rcx+1Ch], 1
0x18001e779  jz      short loc_18001E78C
0x18001e77b  mov     edx, 11h
0x18001e780  mov     r8, r13
0x18001e783  mov     rcx, [rcx+10h]
0x18001e787  call    WPP_SF_
0x18001e78c  mov     rax, [rsi]
0x18001e78f  mov     rcx, rsi
0x18001e792  mov     rax, [rax+38h]
0x18001e796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e79b  jmp     short loc_18001E7C1
0x18001e79d  xor     ebx, ebx
0x18001e79f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7a6  cmp     rcx, r12
0x18001e7a9  jz      short loc_18001E7C1
0x18001e7ab  test    byte ptr [rcx+1Ch], 1
0x18001e7af  jz      short loc_18001E7C1
0x18001e7b1  lea     edx, [rbx+12h]
0x18001e7b4  mov     r8, r13
0x18001e7b7  mov     rcx, [rcx+10h]
0x18001e7bb  call    WPP_SF_
0x18001e7c0  nop
0x18001e7c1  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e7c8  mov     [rbp+57h+var_A0], rax
0x18001e7cc  lea     rcx, [rbp+57h+var_98]
0x18001e7d0  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e7d5  nop
0x18001e7d6  xor     r8d, r8d
0x18001e7d9  mov     dl, 1
0x18001e7db  lea     rcx, [rbp+57h+var_70]
0x18001e7df  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001e7e4  nop
0x18001e7e5  xor     r8d, r8d
0x18001e7e8  mov     dl, 1
0x18001e7ea  lea     rcx, [rbp+57h+var_50]
0x18001e7ee  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001e7f3  nop
0x18001e7f4  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e7fb  mov     [rbp+57h+var_80], rax
0x18001e7ff  lea     rcx, [rbp+57h+var_78]
0x18001e803  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e808  nop
0x18001e809  lea     rcx, [rbp+57h+var_90]
0x18001e80d  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e812  nop
0x18001e813  lea     rcx, [rbp+57h+var_88]
0x18001e817  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e81c  mov     eax, ebx
0x18001e81e  mov     rcx, [rbp+57h+var_30]
0x18001e822  xor     rcx, rsp; StackCookie
0x18001e825  call    __security_check_cookie
0x18001e82a  mov     rbx, [rsp+0C0h+arg_18]
0x18001e832  add     rsp, 0A0h
0x18001e839  pop     r13
0x18001e83b  pop     r12
0x18001e83d  pop     rdi
0x18001e83e  pop     rsi
0x18001e83f  pop     rbp
0x18001e840  retn
```
