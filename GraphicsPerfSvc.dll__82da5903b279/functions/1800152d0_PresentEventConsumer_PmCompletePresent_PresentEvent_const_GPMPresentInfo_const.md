# PresentEventConsumer::PmCompletePresent(PresentEvent const &,GPMPresentInfo const &)

- ea: `0x1800152d0`
- end: `0x180015519`
- name: `?PmCompletePresent@PresentEventConsumer@@UEAAJAEBUPresentEvent@@AEBUGPMPresentInfo@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(PresentEventConsumer *__hidden this, const struct PresentEvent *, const struct GPMPresentInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003ab0`
- `0x180005c6c`
- `0x18000bcc0`
- `0x180014aec`
- `0x1800152d0`
- `0x180015b44`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800153fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800153fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PresentEventConsumer::PmCompletePresent(
        PresentEventConsumer *this,
        const struct PresentEvent *a2,
        const struct GPMPresentInfo *a3)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  __int64 v10; // r8
  __int64 *v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // edi
  int v14; // ecx
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+20h] [rbp-89h] BYREF
  __int64 v17; // [rsp+28h] [rbp-81h] BYREF
  __int64 v18; // [rsp+30h] [rbp-79h] BYREF
  __int64 v19; // [rsp+38h] [rbp-71h]
  __int64 v20; // [rsp+40h] [rbp-69h]
  int v21; // [rsp+48h] [rbp-61h]
  int v22; // [rsp+4Ch] [rbp-5Dh]
  __int64 v23; // [rsp+50h] [rbp-59h]
  __int64 v24; // [rsp+58h] [rbp-51h]
  __int64 v25; // [rsp+60h] [rbp-49h]
  int v26; // [rsp+68h] [rbp-41h]
  int v27; // [rsp+6Ch] [rbp-3Dh]
  __int64 v28; // [rsp+70h] [rbp-39h]
  char v29; // [rsp+78h] [rbp-31h]
  __int16 v30; // [rsp+79h] [rbp-30h]
  char v31; // [rsp+7Bh] [rbp-2Eh]
  int v32; // [rsp+7Ch] [rbp-2Dh]
  _QWORD v33[2]; // [rsp+80h] [rbp-29h] BYREF
  int v34; // [rsp+90h] [rbp-19h]
  int v35; // [rsp+94h] [rbp-15h]
  __int64 v36; // [rsp+98h] [rbp-11h]
  __int128 v37; // [rsp+A0h] [rbp-9h]
  int v38; // [rsp+B0h] [rbp+7h]
  int v39; // [rsp+B4h] [rbp+Bh]
  __int64 v40; // [rsp+B8h] [rbp+Fh]
  __int64 v41; // [rsp+C0h] [rbp+17h]

  v22 = 0;
  v30 = 0;
  v31 = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  v5 = *((_DWORD *)a2 + 40);
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 1 )
          ++*((_DWORD *)this + 45);
      }
      else
      {
        ++*((_DWORD *)this + 43);
      }
    }
    else
    {
      ++*((_DWORD *)this + 42);
    }
  }
  else
  {
    ++*((_DWORD *)this + 44);
  }
  v18 = *(_QWORD *)a2;
  v19 = *((_QWORD *)a2 + 5);
  v20 = *((_QWORD *)a2 + 3);
  v21 = *((_DWORD *)a2 + 14);
  v24 = *(_QWORD *)((char *)a2 + 140);
  v25 = *((_QWORD *)a2 + 6);
  v23 = *((_QWORD *)a2 + 16);
  v26 = *((_DWORD *)a2 + 39);
  v27 = *((_DWORD *)a2 + 46);
  v28 = *((_QWORD *)a2 + 24);
  v29 = *((_BYTE *)a2 + 164);
  v32 = *((_DWORD *)a2 + 40);
  v33[0] = v18;
  v33[1] = v19;
  v40 = v24;
  v39 = v21;
  v36 = v25;
  v34 = *((_DWORD *)a2 + 3);
  v41 = v25;
  if ( (*(unsigned __int8 (__fastcall **)(PresentEventConsumer *))(*(_QWORD *)this + 88LL))(this) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v16 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    std::deque<PresentEventConsumer::PresentData>::push_back((char *)this + 88, v33);
    v8 = *((_QWORD *)this + 15);
    if ( v8 )
    {
      v9 = v19 - 500000;
      while ( 1 )
      {
        v10 = *((_QWORD *)this + 14);
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 8 * (v10 & (*((_QWORD *)this + 13) - 1LL))) + 8LL) >= v9 )
          break;
        *((_QWORD *)this + 15) = --v8;
        if ( !v8 )
        {
          *((_QWORD *)this + 14) = 0;
          break;
        }
        *((_QWORD *)this + 14) = v10 + 1;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v16);
  }
  v11 = (__int64 *)std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
                     (char *)this + 136,
                     &v16);
  v12 = *v11;
  if ( *v11 == *((_QWORD *)this + 17) )
    v12 = *PresentEventConsumer::AddPresentConsumer((__int64 *)this, &v17, v25);
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v12 + 40) + 8LL))(*(_QWORD *)(v12 + 40), &v18);
  (*(void (__fastcall **)(_QWORD, const struct GPMPresentInfo *))(**(_QWORD **)(v12 + 40) + 24LL))(
    *(_QWORD *)(v12 + 40),
    a3);
  if ( v13 )
  {
    v14 = dword_180042E50;
    if ( (unsigned int)dword_180042E50 < 0xA )
    {
      (*(void (__fastcall **)(PresentEventConsumer *, const wchar_t *))(*(_QWORD *)this + 120LL))(
        this,
        L"Bad insert detected.");
      v14 = dword_180042E50;
    }
    dword_180042E50 = v14 + 1;
  }
  return v13;
}

```

## disassembly

```asm
0x1800152d0  push    rbp
0x1800152d2  push    rbx
0x1800152d3  push    rsi
0x1800152d4  push    rdi
0x1800152d5  push    r14
0x1800152d7  lea     rbp, [rsp-37h]
0x1800152dc  sub     rsp, 0E0h
0x1800152e3  mov     rax, cs:__security_cookie
0x1800152ea  xor     rax, rsp
0x1800152ed  mov     [rbp+57h+var_30], rax
0x1800152f1  mov     r14, r8
0x1800152f4  mov     rbx, rdx
0x1800152f7  mov     rsi, rcx
0x1800152fa  mov     [rbp+57h+var_B4], 0
0x180015301  xor     eax, eax
0x180015303  mov     [rbp+57h+var_87], ax
0x180015307  mov     [rbp+57h+var_85], al
0x18001530a  mov     [rbp+57h+var_6C], eax
0x18001530d  xorps   xmm0, xmm0
0x180015310  movdqa  [rbp+57h+var_60], xmm0
0x180015315  mov     [rbp+57h+var_50], eax
0x180015318  mov     ecx, [rdx+0A0h]
0x18001531e  test    ecx, ecx
0x180015320  jz      short loc_180015349
0x180015322  sub     ecx, 1
0x180015325  jz      short loc_180015341
0x180015327  sub     ecx, 1
0x18001532a  jz      short loc_180015339
0x18001532c  cmp     ecx, 1
0x18001532f  jnz     short loc_18001534F
0x180015331  inc     dword ptr [rsi+0B4h]
0x180015337  jmp     short loc_18001534F
0x180015339  inc     dword ptr [rsi+0ACh]
0x18001533f  jmp     short loc_18001534F
0x180015341  inc     dword ptr [rsi+0A8h]
0x180015347  jmp     short loc_18001534F
0x180015349  inc     dword ptr [rsi+0B0h]
0x18001534f  mov     r11, [rdx]
0x180015352  mov     [rbp+57h+var_D0], r11
0x180015356  mov     r10, [rdx+28h]
0x18001535a  mov     [rbp+57h+var_C8], r10
0x18001535e  mov     rax, [rdx+18h]
0x180015362  mov     [rbp+57h+var_C0], rax
0x180015366  mov     r9d, [rdx+38h]
0x18001536a  mov     [rbp+57h+var_B8], r9d
0x18001536e  mov     edx, [rdx+8Ch]
0x180015374  mov     dword ptr [rbp+57h+var_A8], edx
0x180015377  mov     ecx, [rbx+90h]
0x18001537d  mov     dword ptr [rbp+57h+var_A8+4], ecx
0x180015380  mov     r8, [rbx+30h]
0x180015384  mov     [rbp+57h+var_A0], r8
0x180015388  mov     rax, [rbx+80h]
0x18001538f  mov     [rbp+57h+var_B0], rax
0x180015393  mov     eax, [rbx+9Ch]
0x180015399  mov     [rbp+57h+var_98], eax
0x18001539c  mov     eax, [rbx+0B8h]
0x1800153a2  mov     [rbp+57h+var_94], eax
0x1800153a5  mov     rax, [rbx+0C0h]
0x1800153ac  mov     [rbp+57h+var_90], rax
0x1800153b0  mov     al, [rbx+0A4h]
0x1800153b6  mov     [rbp+57h+var_88], al
0x1800153b9  mov     eax, [rbx+0A0h]
0x1800153bf  mov     [rbp+57h+var_84], eax
0x1800153c2  mov     [rbp+57h+var_80], r11
0x1800153c6  mov     [rbp+57h+var_78], r10
0x1800153ca  mov     dword ptr [rbp+57h+var_48], edx
0x1800153cd  mov     dword ptr [rbp+57h+var_48+4], ecx
0x1800153d0  mov     [rbp+57h+var_4C], r9d
0x1800153d4  mov     [rbp+57h+var_68], r8
0x1800153d8  mov     eax, [rbx+0Ch]
0x1800153db  mov     [rbp+57h+var_70], eax
0x1800153de  mov     [rbp+57h+var_40], r8
0x1800153e2  mov     rax, [rsi]
0x1800153e5  mov     rcx, rsi
0x1800153e8  mov     rax, [rax+58h]
0x1800153ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153f1  test    al, al
0x1800153f3  jz      short loc_18001546A
0x1800153f5  lea     rbx, [rsi+8]
0x1800153f9  mov     rcx, rbx; lpCriticalSection
0x1800153fc  call    cs:__imp_EnterCriticalSection
0x180015402  mov     [rsp+100h+var_E0], rbx
0x180015407  lea     rcx, [rsi+58h]
0x18001540b  lea     rdx, [rbp+57h+var_80]
0x18001540f  call    ?push_back@?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAAXAEBUPresentData@PresentEventConsumer@@@Z; std::deque<PresentEventConsumer::PresentData>::push_back(PresentEventConsumer::PresentData const &)
0x180015414  mov     rdx, [rsi+78h]
0x180015418  test    rdx, rdx
0x18001541b  jz      short loc_180015460
0x18001541d  mov     r9, [rbp+57h+var_C8]
0x180015421  add     r9, 0FFFFFFFFFFF85EE0h
0x180015428  mov     r8, [rsi+70h]
0x18001542c  mov     rcx, [rsi+68h]
0x180015430  dec     rcx
0x180015433  and     rcx, r8
0x180015436  mov     rax, [rsi+60h]
0x18001543a  mov     rcx, [rax+rcx*8]
0x18001543e  cmp     [rcx+8], r9
0x180015442  jnb     short loc_180015460
0x180015444  sub     rdx, 1
0x180015448  mov     [rsi+78h], rdx
0x18001544c  jz      short loc_180015458
0x18001544e  lea     rax, [r8+1]
0x180015452  mov     [rsi+70h], rax
0x180015456  jmp     short loc_180015428
0x180015458  mov     qword ptr [rsi+70h], 0
0x180015460  lea     rcx, [rsp+100h+var_E0]
0x180015465  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001546a  lea     rdi, [rsi+88h]
0x180015471  lea     r8, [rbp+57h+var_A0]
0x180015475  lea     rdx, [rsp+100h+var_E0]
0x18001547a  mov     rcx, rdi
0x18001547d  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x180015482  mov     rbx, [rax]
0x180015485  cmp     rbx, [rdi]
0x180015488  jnz     short loc_18001549E
0x18001548a  mov     r8, [rbp+57h+var_A0]
0x18001548e  lea     rdx, [rsp+100h+var_D8]
0x180015493  mov     rcx, rsi
0x180015496  call    ?AddPresentConsumer@PresentEventConsumer@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@@std@@_K@Z; PresentEventConsumer::AddPresentConsumer(unsigned __int64)
0x18001549b  mov     rbx, [rax]
0x18001549e  mov     rcx, [rbx+28h]
0x1800154a2  mov     rax, [rcx]
0x1800154a5  lea     rdx, [rbp+57h+var_D0]
0x1800154a9  mov     rax, [rax+8]
0x1800154ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b2  mov     edi, eax
0x1800154b4  mov     r8, [rbx+28h]
0x1800154b8  mov     rcx, [r8]
0x1800154bb  mov     rax, [rcx+18h]
0x1800154bf  mov     rdx, r14
0x1800154c2  mov     rcx, r8
0x1800154c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ca  test    edi, edi
0x1800154cc  jz      short loc_1800154FD
0x1800154ce  mov     ecx, cs:dword_180042E50
0x1800154d4  cmp     ecx, 0Ah
0x1800154d7  jnb     short loc_1800154F5
0x1800154d9  mov     rax, [rsi]
0x1800154dc  lea     rdx, aBadInsertDetec; "Bad insert detected."
0x1800154e3  mov     rcx, rsi
0x1800154e6  mov     rax, [rax+78h]
0x1800154ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ef  mov     ecx, cs:dword_180042E50
0x1800154f5  inc     ecx
0x1800154f7  mov     cs:dword_180042E50, ecx
0x1800154fd  mov     eax, edi
0x1800154ff  mov     rcx, [rbp+57h+var_30]
0x180015503  xor     rcx, rsp; StackCookie
0x180015506  call    __security_check_cookie
0x18001550b  add     rsp, 0E0h
0x180015512  pop     r14
0x180015514  pop     rdi
0x180015515  pop     rsi
0x180015516  pop     rbx
0x180015517  pop     rbp
0x180015518  retn
```
