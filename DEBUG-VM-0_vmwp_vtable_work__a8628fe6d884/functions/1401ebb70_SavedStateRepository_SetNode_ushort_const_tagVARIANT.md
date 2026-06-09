# SavedStateRepository::SetNode(ushort const *,tagVARIANT)

- ea: `0x1401ebb70`
- end: `0x1401ebd8e`
- name: `?SetNode@SavedStateRepository@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400a20f0`

## callees

- `0x140132940`
- `0x1401eaed0`
- `0x1401eb5d4`
- `0x1401ebb70`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ebb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ebb95`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ebc86`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ebc86`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ebc69`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ebc69`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ebc4e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ebc4e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ebccb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ebccb`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall SavedStateRepository::SetNode(
        SavedStateRepository *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int NodeForRollback; // ebx
  SAFEARRAY *parray; // r14
  int v8; // eax
  struct tagVARIANT *v10[2]; // [rsp+30h] [rbp-48h] BYREF
  void *ppvData[2]; // [rsp+40h] [rbp-38h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 33) != GetCurrentThreadId() )
    return (unsigned int)-2147418113;
  v10[0] = 0;
  NodeForRollback = SavedStateRepository::GetNodeForRollback(this, a2, v10);
  if ( NodeForRollback < 0 )
    return (unsigned int)NodeForRollback;
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 13) + 168LL))(*((_QWORD *)this + 13), a2);
  if ( a3->vt == 5 )
  {
    NodeForRollback = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 13) + 112LL))(
                        *((_QWORD *)this + 13),
                        a2);
  }
  else
  {
    switch ( a3->vt )
    {
      case 8u:
        v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, LONGLONG))(**((_QWORD **)this + 13) + 128LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->llVal);
        break;
      case 0xBu:
        v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, bool))(**((_QWORD **)this + 13) + 96LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->iVal == -1);
        break;
      case 0x14u:
        v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, LONGLONG))(**((_QWORD **)this + 13) + 64LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->llVal);
        break;
      case 0x2011u:
        ppvData[0] = 0;
        plLbound = 0;
        parray = a3->parray;
        SafeArrayAccessData(parray, ppvData);
        SafeArrayGetLBound(parray, 1u, &plLbound);
        if ( plLbound )
        {
          NodeForRollback = -2147024809;
        }
        else
        {
          SafeArrayGetUBound(parray, 1u, &plLbound);
          ++plLbound;
          NodeForRollback = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, void *))(**((_QWORD **)this + 13)
                                                                                          + 144LL))(
                              *((_QWORD *)this + 13),
                              a2,
                              ppvData[0]);
        }
        SafeArrayUnaccessData(parray);
        goto LABEL_19;
      default:
        return (unsigned int)-2147467259;
    }
    NodeForRollback = v8;
  }
LABEL_19:
  if ( NodeForRollback >= 0 )
  {
    ppvData[0] = a2;
    ppvData[1] = v10[0];
    std::map<std::wstring,tagVARIANT *>::insert<std::pair<unsigned short const *,tagVARIANT *>,0>(
      (char *)this + 112,
      v10,
      ppvData);
  }
  return (unsigned int)NodeForRollback;
}

```

## disassembly

```asm
0x1401ebb70  mov     [rsp+arg_18], rbx
0x1401ebb75  push    rsi
0x1401ebb76  push    rdi
0x1401ebb77  push    r14
0x1401ebb79  sub     rsp, 60h
0x1401ebb7d  mov     rax, cs:__security_cookie
0x1401ebb84  xor     rax, rsp
0x1401ebb87  mov     [rsp+78h+var_20], rax
0x1401ebb8c  mov     r14, r8
0x1401ebb8f  mov     rsi, rdx
0x1401ebb92  mov     rdi, rcx
0x1401ebb95  call    cs:__imp_GetCurrentThreadId
0x1401ebb9c  nop     dword ptr [rax+rax+00h]
0x1401ebba1  mov     r8d, [rdi+84h]
0x1401ebba8  cmp     r8d, eax
0x1401ebbab  jz      short loc_1401EBBB7
0x1401ebbad  mov     ebx, 8000FFFFh
0x1401ebbb2  jmp     loc_1401EBD67
0x1401ebbb7  mov     [rsp+78h+var_48], 0
0x1401ebbc0  lea     r8, [rsp+78h+var_48]; struct tagVARIANT **
0x1401ebbc5  mov     rdx, rsi; unsigned __int16 *
0x1401ebbc8  mov     rcx, rdi; this
0x1401ebbcb  call    ?GetNodeForRollback@SavedStateRepository@@AEAAJPEBGAEAPEAUtagVARIANT@@@Z; SavedStateRepository::GetNodeForRollback(ushort const *,tagVARIANT * &)
0x1401ebbd0  mov     ebx, eax
0x1401ebbd2  test    eax, eax
0x1401ebbd4  js      loc_1401EBD67
0x1401ebbda  mov     rcx, [rdi+68h]
0x1401ebbde  mov     rax, [rcx]
0x1401ebbe1  mov     rdx, rsi
0x1401ebbe4  mov     rax, [rax+0A8h]
0x1401ebbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebbf0  cmp     word ptr [r14], 5
0x1401ebbf5  jz      loc_1401EBD26
0x1401ebbfb  cmp     word ptr [r14], 8
0x1401ebc00  jz      loc_1401EBD08
0x1401ebc06  cmp     word ptr [r14], 0Bh
0x1401ebc0b  jz      loc_1401EBCE6
0x1401ebc11  cmp     word ptr [r14], 14h
0x1401ebc16  jz      loc_1401EBCD9
0x1401ebc1c  mov     eax, 2011h
0x1401ebc21  cmp     [r14], ax
0x1401ebc25  jz      short loc_1401EBC31
0x1401ebc27  mov     ebx, 80004005h
0x1401ebc2c  jmp     loc_1401EBD67
0x1401ebc31  mov     [rsp+78h+ppvData], 0
0x1401ebc3a  mov     [rsp+78h+plLbound], 0
0x1401ebc42  mov     r14, [r14+8]
0x1401ebc46  lea     rdx, [rsp+78h+ppvData]; ppvData
0x1401ebc4b  mov     rcx, r14; psa
0x1401ebc4e  call    cs:__imp_SafeArrayAccessData
0x1401ebc55  nop     dword ptr [rax+rax+00h]
0x1401ebc5a  lea     r8, [rsp+78h+plLbound]; plLbound
0x1401ebc5f  mov     ebx, 1
0x1401ebc64  mov     edx, ebx; nDim
0x1401ebc66  mov     rcx, r14; psa
0x1401ebc69  call    cs:__imp_SafeArrayGetLBound
0x1401ebc70  nop     dword ptr [rax+rax+00h]
0x1401ebc75  cmp     [rsp+78h+plLbound], 0
0x1401ebc7a  jnz     short loc_1401EBCC3
0x1401ebc7c  lea     r8, [rsp+78h+plLbound]; plUbound
0x1401ebc81  mov     edx, ebx; nDim
0x1401ebc83  mov     rcx, r14; psa
0x1401ebc86  call    cs:__imp_SafeArrayGetUBound
0x1401ebc8d  nop     dword ptr [rax+rax+00h]
0x1401ebc92  mov     r9d, [rsp+78h+plLbound]
0x1401ebc97  add     r9d, ebx
0x1401ebc9a  mov     [rsp+78h+plLbound], r9d
0x1401ebc9f  mov     rcx, [rdi+68h]
0x1401ebca3  mov     rax, [rcx]
0x1401ebca6  mov     [rsp+78h+var_58], r9d
0x1401ebcab  mov     r8, [rsp+78h+ppvData]
0x1401ebcb0  mov     rdx, rsi
0x1401ebcb3  mov     rax, [rax+90h]
0x1401ebcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebcbf  mov     ebx, eax
0x1401ebcc1  jmp     short loc_1401EBCC8
0x1401ebcc3  mov     ebx, 80070057h
0x1401ebcc8  mov     rcx, r14; psa
0x1401ebccb  call    cs:__imp_SafeArrayUnaccessData
0x1401ebcd2  nop     dword ptr [rax+rax+00h]
0x1401ebcd7  jmp     short loc_1401EBD41
0x1401ebcd9  mov     rcx, [rdi+68h]
0x1401ebcdd  mov     rax, [rcx]
0x1401ebce0  mov     rax, [rax+40h]
0x1401ebce4  jmp     short loc_1401EBD16
0x1401ebce6  mov     rcx, [rdi+68h]
0x1401ebcea  mov     rax, [rcx]
0x1401ebced  xor     r8d, r8d
0x1401ebcf0  cmp     word ptr [r14+8], 0FFFFh
0x1401ebcf6  setz    r8b
0x1401ebcfa  mov     rdx, rsi
0x1401ebcfd  mov     rax, [rax+60h]
0x1401ebd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebd06  jmp     short loc_1401EBD22
0x1401ebd08  mov     rcx, [rdi+68h]
0x1401ebd0c  mov     rax, [rcx]
0x1401ebd0f  mov     rax, [rax+80h]
0x1401ebd16  mov     rdx, rsi
0x1401ebd19  mov     r8, [r14+8]
0x1401ebd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebd22  mov     ebx, eax
0x1401ebd24  jmp     short loc_1401EBD41
0x1401ebd26  mov     rcx, [rdi+68h]
0x1401ebd2a  mov     rax, [rcx]
0x1401ebd2d  movsd   xmm2, qword ptr [r14+8]
0x1401ebd33  mov     rdx, rsi
0x1401ebd36  mov     rax, [rax+70h]
0x1401ebd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebd3f  mov     ebx, eax
0x1401ebd41  test    ebx, ebx
0x1401ebd43  js      short loc_1401EBD67
0x1401ebd45  mov     [rsp+78h+ppvData], rsi
0x1401ebd4a  mov     rax, [rsp+78h+var_48]
0x1401ebd4f  mov     [rsp+78h+var_30], rax
0x1401ebd54  lea     rcx, [rdi+70h]
0x1401ebd58  lea     r8, [rsp+78h+ppvData]
0x1401ebd5d  lea     rdx, [rsp+78h+var_48]
0x1401ebd62  call    ??$insert@U?$pair@PEBGPEAUtagVARIANT@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGPEAUtagVARIANT@@@1@@Z; std::map<std::wstring,tagVARIANT *>::insert<std::pair<ushort const *,tagVARIANT *>,0>(std::pair<ushort const *,tagVARIANT *> &&)
0x1401ebd67  mov     eax, ebx
0x1401ebd69  jmp     short loc_1401EBD6F
0x1401ebd6b  mov     eax, [rsp+78h+plLbound]
0x1401ebd6f  mov     rcx, [rsp+78h+var_20]
0x1401ebd74  xor     rcx, rsp; StackCookie
0x1401ebd77  call    __security_check_cookie
0x1401ebd7c  mov     rbx, [rsp+78h+arg_18]
0x1401ebd84  add     rsp, 60h
0x1401ebd88  pop     r14
0x1401ebd8a  pop     rdi
0x1401ebd8b  pop     rsi
0x1401ebd8c  retn
```
