# ResourcePackResolver::CategorizeMainPackage(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &)

- ea: `0x180002c70`
- end: `0x18000309b`
- name: `?CategorizeMainPackage@ResourcePackResolver@@IEAAXAEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180001fd0`

## callees

- `0x180002c70`
- `0x1800030b0`
- `0x1800038d8`
- `0x180003940`
- `0x18000d6f4`
- `0x18000d84c`
- `0x18000db80`
- `0x180025010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e16`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ResourcePackResolver::CategorizeMainPackage(__int64 *a1, _QWORD *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD **); // rdi
  int v9; // edx
  int v10; // ecx
  int v11; // ebx
  int v12; // edx
  int v13; // ecx
  int v14; // ebx
  __int64 v15; // rax
  int v16; // edx
  int v17; // ecx
  int v18; // ebx
  __int64 v19; // rax
  int v20; // edx
  int v21; // ecx
  int v22; // ebx
  __int64 *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  int v26; // r8d
  _DWORD *v27; // r11
  __int64 **v28; // rcx
  __int64 *v29; // rdx
  __int64 *v30; // r9
  __int64 *j; // rax
  unsigned int v32; // r10d
  __int64 *i; // rcx
  int v34; // [rsp+20h] [rbp-50h]
  __int64 *v35; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v37[2]; // [rsp+40h] [rbp-30h] BYREF
  char v38; // [rsp+50h] [rbp-20h] BYREF
  char v39; // [rsp+58h] [rbp-18h] BYREF
  char v40[16]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v42; // [rsp+A0h] [rbp+30h] BYREF
  int v43; // [rsp+B0h] [rbp+40h] BYREF
  _QWORD *v44; // [rsp+B8h] [rbp+48h] BYREF

  v37[1] = -2;
  v4 = 0;
  v44 = 0;
  if ( !*a1 )
  {
    v5 = *a2;
    if ( *a2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*a2);
      v6 = *a1;
      *a1 = v5;
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v4 = v44;
    }
    v7 = *a2;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)*a2 + 64LL);
    if ( v4 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v4 + 16LL))(v4, *v4);
    }
    v11 = v8(v7, &v44);
    if ( v11 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v10,
        v9,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        70,
        94);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v11,
        v34);
    v42 = 0;
    (*(void (__fastcall **)(_QWORD *, int *))(*v44 + 32LL))(v44, &v42);
    if ( v42 )
    {
      while ( 1 )
      {
        v35 = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(*v44 + 24LL))(v44, &v35);
        if ( v14 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
          McTemplateU0zqd_EventWriteTransfer(
            v13,
            v12,
            (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            75,
            94);
        if ( v14 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            (const char *)(unsigned int)v14,
            v34);
        pv = 0;
        v15 = *v35;
        pv = 0;
        v18 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v15 + 24))(v35, &pv);
        if ( v18 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
          McTemplateU0zqd_EventWriteTransfer(
            v17,
            v16,
            (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            78,
            94);
        if ( v18 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x4E,
            (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            (const char *)(unsigned int)v18,
            v34);
        if ( pv )
        {
          v37[0] = pv;
          v19 = std::_Tree_val<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<unsigned short *>(
                  a1 + 33,
                  v37);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(
            a1 + 33,
            v40,
            v19);
        }
        v43 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v35 + 32))(v35, &v43);
        if ( v22 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
          McTemplateU0zqd_EventWriteTransfer(
            v21,
            v20,
            (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            85,
            94);
        if ( v22 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x55,
            (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
            (const char *)(unsigned int)v22,
            v34);
        if ( !v43 )
          goto LABEL_20;
        v25 = std::_Tree_val<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Buynode<unsigned int &>(
                a1 + 37,
                &v43);
        v27 = (_DWORD *)v25;
        v28 = (__int64 **)a1[38];
        v29 = v28[1];
        if ( *((_BYTE *)v29 + 29) )
        {
          LOBYTE(v26) = 1;
          v30 = (__int64 *)a1[38];
        }
        else
        {
          v32 = *(_DWORD *)(v25 + 24);
          do
          {
            v30 = v29;
            LOBYTE(v26) = v32 < *((_DWORD *)v29 + 6);
            if ( v32 < *((_DWORD *)v29 + 6) )
              v29 = (__int64 *)*v29;
            else
              v29 = (__int64 *)v29[2];
          }
          while ( !*((_BYTE *)v29 + 29) );
        }
        j = v30;
        if ( !(_BYTE)v26 )
          goto LABEL_38;
        if ( v30 != *v28 )
          break;
        LOBYTE(v26) = 1;
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert(
          (_DWORD)a1 + 296,
          (unsigned int)&v38,
          v26,
          (_DWORD)v30,
          (__int64)v27);
LABEL_20:
        if ( pv )
          CoTaskMemFree(pv);
        v23 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
        }
        (*(void (__fastcall **)(_QWORD *, int *))(*v44 + 40LL))(v44, &v42);
        if ( !v42 )
          goto LABEL_25;
      }
      if ( *((_BYTE *)v30 + 29) )
      {
        j = (__int64 *)v30[2];
      }
      else if ( *(_BYTE *)(*v30 + 29) )
      {
        for ( i = (__int64 *)v30[1]; !*((_BYTE *)i + 29); i = (__int64 *)i[1] )
        {
          if ( j != (__int64 *)*i )
            break;
          j = i;
        }
        if ( !*((_BYTE *)j + 29) )
          j = i;
      }
      else
      {
        for ( j = (__int64 *)*v30; !*(_BYTE *)(j[2] + 29); j = (__int64 *)j[2] )
          ;
      }
LABEL_38:
      if ( *((_DWORD *)j + 6) >= v27[6] )
        operator delete(v27);
      else
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert(
          (_DWORD)a1 + 296,
          (unsigned int)&v39,
          v26,
          (_DWORD)v30,
          (__int64)v27);
      goto LABEL_20;
    }
LABEL_25:
    v24 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    }
  }
}

```

## disassembly

```asm
0x180002c70  push    rbp
0x180002c72  push    rbx
0x180002c73  push    rsi
0x180002c74  push    rdi
0x180002c75  push    r14
0x180002c77  mov     rbp, rsp
0x180002c7a  sub     rsp, 70h
0x180002c7e  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180002c86  mov     rdi, rdx
0x180002c89  mov     rsi, rcx
0x180002c8c  xor     r14d, r14d
0x180002c8f  mov     ecx, r14d
0x180002c92  mov     [rbp+arg_18], rcx
0x180002c96  cmp     [rsi], r14
0x180002c99  jnz     loc_180002F79
0x180002c9f  mov     rbx, [rdx]
0x180002ca2  test    rbx, rbx
0x180002ca5  jz      short loc_180002CD3
0x180002ca7  mov     rax, [rbx]
0x180002caa  mov     rcx, rbx
0x180002cad  mov     rax, [rax+8]
0x180002cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb6  nop
0x180002cb7  mov     rcx, [rsi]
0x180002cba  mov     [rsi], rbx
0x180002cbd  test    rcx, rcx
0x180002cc0  jz      short loc_180002CCF
0x180002cc2  mov     rax, [rcx]
0x180002cc5  mov     rax, [rax+10h]
0x180002cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cce  nop
0x180002ccf  mov     rcx, [rbp+arg_18]
0x180002cd3  mov     rbx, [rdi]
0x180002cd6  mov     rax, [rbx]
0x180002cd9  mov     rdi, [rax+40h]
0x180002cdd  test    rcx, rcx
0x180002ce0  jz      short loc_180002CF3
0x180002ce2  mov     [rbp+arg_18], r14
0x180002ce6  mov     rdx, [rcx]
0x180002ce9  mov     rax, [rdx+10h]
0x180002ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf2  nop
0x180002cf3  lea     rdx, [rbp+arg_18]
0x180002cf7  mov     rcx, rbx
0x180002cfa  mov     rax, rdi
0x180002cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d02  mov     ebx, eax
0x180002d04  cmp     eax, 8007065Eh
0x180002d09  jz      loc_180002F84
0x180002d0f  mov     rcx, [rbp+28h]; this
0x180002d13  test    ebx, ebx
0x180002d15  js      loc_180002F64
0x180002d1b  mov     [rbp+arg_0], r14d
0x180002d1f  mov     rcx, [rbp+arg_18]
0x180002d23  mov     rax, [rcx]
0x180002d26  lea     rdx, [rbp+arg_0]
0x180002d2a  mov     rax, [rax+20h]
0x180002d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d33  cmp     [rbp+arg_0], 0
0x180002d37  jz      loc_180002E55
0x180002d3d  nop     dword ptr [rax]
0x180002d40  mov     [rbp+var_40], r14
0x180002d44  mov     rcx, [rbp+arg_18]
0x180002d48  mov     rax, [rcx]
0x180002d4b  lea     rdx, [rbp+var_40]
0x180002d4f  mov     rax, [rax+18h]
0x180002d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d58  mov     ebx, eax
0x180002d5a  cmp     eax, 8007065Eh
0x180002d5f  jz      loc_180002FB0
0x180002d65  mov     rcx, [rbp+28h]; this
0x180002d69  test    ebx, ebx
0x180002d6b  js      loc_180002F4F
0x180002d71  mov     [rbp+pv], r14
0x180002d75  mov     rcx, [rbp+var_40]
0x180002d79  mov     rax, [rcx]
0x180002d7c  mov     [rbp+pv], r14
0x180002d80  lea     rdx, [rbp+pv]
0x180002d84  mov     rax, [rax+18h]
0x180002d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8d  mov     ebx, eax
0x180002d8f  cmp     eax, 8007065Eh
0x180002d94  jz      loc_180002FDC
0x180002d9a  mov     rcx, [rbp+28h]; this
0x180002d9e  test    ebx, ebx
0x180002da0  js      loc_180002F3A
0x180002da6  mov     rax, [rbp+pv]
0x180002daa  test    rax, rax
0x180002dad  jz      short loc_180002DD6
0x180002daf  mov     [rbp+var_30], rax
0x180002db3  lea     rdx, [rbp+var_30]
0x180002db7  lea     rcx, [rsi+108h]
0x180002dbe  call    ??$_Buynode@PEAG@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@$$QEAPEAG@Z; std::_Tree_val<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Buynode<ushort *>(ushort * &&)
0x180002dc3  mov     r8, rax
0x180002dc6  lea     rdx, [rbp+var_10]
0x180002dca  lea     rcx, [rsi+108h]
0x180002dd1  call    ?_Linsert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,bool)
0x180002dd6  mov     [rbp+arg_10], r14d
0x180002dda  mov     rcx, [rbp+var_40]
0x180002dde  mov     rax, [rcx]
0x180002de1  lea     rdx, [rbp+arg_10]
0x180002de5  mov     rax, [rax+20h]
0x180002de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dee  mov     ebx, eax
0x180002df0  cmp     eax, 8007065Eh
0x180002df5  jz      loc_180003008
0x180002dfb  mov     rcx, [rbp+28h]; this
0x180002dff  test    ebx, ebx
0x180002e01  js      loc_180002F25
0x180002e07  cmp     [rbp+arg_10], 0
0x180002e0b  jnz     short loc_180002E7A
0x180002e0d  mov     rcx, [rbp+pv]; pv
0x180002e11  test    rcx, rcx
0x180002e14  jz      short loc_180002E1D
0x180002e16  call    cs:__imp_CoTaskMemFree
0x180002e1c  nop
0x180002e1d  mov     rcx, [rbp+var_40]
0x180002e21  test    rcx, rcx
0x180002e24  jz      short loc_180002E37
0x180002e26  mov     [rbp+var_40], r14
0x180002e2a  mov     rax, [rcx]
0x180002e2d  mov     rax, [rax+10h]
0x180002e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e36  nop
0x180002e37  mov     rcx, [rbp+arg_18]
0x180002e3b  mov     rax, [rcx]
0x180002e3e  lea     rdx, [rbp+arg_0]
0x180002e42  mov     rax, [rax+28h]
0x180002e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4b  cmp     [rbp+arg_0], 0
0x180002e4f  jnz     loc_180002D40
0x180002e55  mov     rcx, [rbp+arg_18]
0x180002e59  test    rcx, rcx
0x180002e5c  jz      short loc_180002E6F
0x180002e5e  mov     [rbp+arg_18], r14
0x180002e62  mov     rax, [rcx]
0x180002e65  mov     rax, [rax+10h]
0x180002e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6e  nop
0x180002e6f  add     rsp, 70h
0x180002e73  pop     r14
0x180002e75  pop     rdi
0x180002e76  pop     rsi
0x180002e77  pop     rbx
0x180002e78  pop     rbp
0x180002e79  retn
0x180002e7a  lea     rdx, [rbp+arg_10]
0x180002e7e  lea     rcx, [rsi+128h]
0x180002e85  call    ??$_Buynode@AEAI@?$_Tree_val@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@1@AEAI@Z; std::_Tree_val<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Buynode<uint &>(uint &)
0x180002e8a  mov     r11, rax
0x180002e8d  mov     rcx, [rsi+130h]
0x180002e94  mov     rdx, [rcx+8]
0x180002e98  cmp     byte ptr [rdx+1Dh], 0
0x180002e9c  jz      short loc_180002ED2
0x180002e9e  mov     r8b, 1
0x180002ea1  mov     r9, rcx
0x180002ea4  mov     rax, r9
0x180002ea7  test    r8b, r8b
0x180002eaa  jz      short loc_180002EEF
0x180002eac  cmp     r9, [rcx]
0x180002eaf  jnz     loc_180003034
0x180002eb5  mov     qword ptr [rsp+70h+var_50], r11
0x180002eba  mov     r8b, 1
0x180002ebd  lea     rdx, [rbp+var_20]
0x180002ec1  lea     rcx, [rsi+128h]
0x180002ec8  call    ?_Insert@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@2@1@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Node *)
0x180002ecd  jmp     loc_180002E0D
0x180002ed2  mov     r10d, [rax+18h]
0x180002ed6  mov     r9, rdx
0x180002ed9  cmp     r10d, [rdx+18h]
0x180002edd  setb    r8b
0x180002ee1  jb      short loc_180002F12
0x180002ee3  mov     rdx, [rdx+10h]
0x180002ee7  cmp     byte ptr [rdx+1Dh], 0
0x180002eeb  jnz     short loc_180002EA4
0x180002eed  jmp     short loc_180002ED6
0x180002eef  mov     ecx, [r11+18h]
0x180002ef3  cmp     [rax+18h], ecx
0x180002ef6  jnb     short loc_180002F17
0x180002ef8  mov     qword ptr [rsp+70h+var_50], r11
0x180002efd  lea     rdx, [rbp+var_18]
0x180002f01  lea     rcx, [rsi+128h]
0x180002f08  call    ?_Insert@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@2@1@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Node *)
0x180002f0d  jmp     loc_180002E0D
0x180002f12  mov     rdx, [rdx]
0x180002f15  jmp     short loc_180002EE7
0x180002f17  mov     rcx, r11
0x180002f1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f20  jmp     loc_180002E0D
0x180002f25  mov     r9d, ebx; char *
0x180002f28  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002f2f  mov     edx, 55h ; 'U'; void *
0x180002f34  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002f3a  mov     r9d, ebx; char *
0x180002f3d  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002f44  mov     edx, 4Eh ; 'N'; void *
0x180002f49  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002f4f  mov     r9d, ebx; char *
0x180002f52  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002f59  mov     edx, 4Bh ; 'K'; void *
0x180002f5e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002f64  mov     r9d, ebx; char *
0x180002f67  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002f6e  mov     edx, 46h ; 'F'; void *
0x180002f73  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002f79  add     rsp, 70h
0x180002f7d  pop     r14
0x180002f7f  pop     rdi
0x180002f80  pop     rsi
0x180002f81  pop     rbx
0x180002f82  pop     rbp
0x180002f83  retn
0x180002f84  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x180002f8b  jz      loc_180002D0F
0x180002f91  mov     [rsp+70h+var_50], 8007065Eh
0x180002f99  mov     r9d, 46h ; 'F'
0x180002f9f  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002fa6  call    McTemplateU0zqd_EventWriteTransfer
0x180002fab  jmp     loc_180002D0F
0x180002fb0  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x180002fb7  jz      loc_180002D65
0x180002fbd  mov     [rsp+70h+var_50], 8007065Eh
0x180002fc5  mov     r9d, 4Bh ; 'K'
0x180002fcb  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002fd2  call    McTemplateU0zqd_EventWriteTransfer
0x180002fd7  jmp     loc_180002D65
0x180002fdc  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x180002fe3  jz      loc_180002D9A
0x180002fe9  mov     [rsp+70h+var_50], 8007065Eh
0x180002ff1  mov     r9d, 4Eh ; 'N'
0x180002ff7  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002ffe  call    McTemplateU0zqd_EventWriteTransfer
0x180003003  jmp     loc_180002D9A
0x180003008  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000300f  jz      loc_180002DFB
0x180003015  mov     [rsp+70h+var_50], 8007065Eh
0x18000301d  mov     r9d, 55h ; 'U'
0x180003023  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000302a  call    McTemplateU0zqd_EventWriteTransfer
0x18000302f  jmp     loc_180002DFB
0x180003034  cmp     byte ptr [r9+1Dh], 0
0x180003039  jz      short loc_180003044
0x18000303b  mov     rax, [r9+10h]
0x18000303f  jmp     loc_180002EEF
0x180003044  mov     rcx, [r9]
0x180003047  cmp     byte ptr [rcx+1Dh], 0
0x18000304b  jnz     short loc_180003071
0x18000304d  mov     rax, rcx
0x180003050  mov     rcx, [rcx+10h]
0x180003054  cmp     byte ptr [rcx+1Dh], 0
0x180003058  jnz     loc_180002EEF
0x18000305e  mov     rax, [rax+10h]
0x180003062  mov     rcx, [rax+10h]
0x180003066  cmp     byte ptr [rcx+1Dh], 0
0x18000306a  jz      short loc_18000305E
0x18000306c  jmp     loc_180002EEF
0x180003071  mov     rcx, [r9+8]
0x180003075  cmp     byte ptr [rcx+1Dh], 0
0x180003079  jnz     short loc_18000308D
0x18000307b  cmp     rax, [rcx]
0x18000307e  jnz     short loc_18000308D
0x180003080  mov     rax, rcx
0x180003083  mov     rcx, [rcx+8]
0x180003087  cmp     byte ptr [rcx+1Dh], 0
0x18000308b  jz      short loc_18000307B
0x18000308d  cmp     byte ptr [rax+1Dh], 0
0x180003091  cmovz   rax, rcx
0x180003095  jmp     loc_180002EEF
```
