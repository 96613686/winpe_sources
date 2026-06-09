# ipx::mtf::MtfTransportServerCoreUI::MtfTransportServerCoreUI(ipx::mtf::MtfTransportType,IMtfTransportServer *)

- ea: `0x18001ed80`
- end: `0x18001f124`
- name: `??0MtfTransportServerCoreUI@mtf@ipx@@QEAA@W4MtfTransportType@12@PEAUIMtfTransportServer@@@Z`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001fb10`

## callees

- `0x180001fc4`
- `0x1800046d4`
- `0x18000cbe4`
- `0x18001031c`
- `0x18001e224`
- `0x18001ed80`
- `0x18001fc54`
- `0x1800236cc`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ef29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ef29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ipx::mtf::MtfTransportServerCoreUI::MtfTransportServerCoreUI(__int64 a1, int a2, __int64 a3)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  _DWORD *v6; // rax
  unsigned int v7; // r8d
  _DWORD *v8; // rbx
  HANDLE EventW; // r14
  void *v10; // rcx
  __int64 v11; // rcx
  int v12; // edx
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  int v15; // edx
  const unsigned __int16 *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  int v22; // [rsp+20h] [rbp-E0h]
  _QWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+48h] [rbp-B8h]
  unsigned __int16 Src[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *(_DWORD *)(a1 + 24) = 0;
  *(_QWORD *)a1 = &ipx::mtf::MtfTransportServerCoreUI::`vftable';
  *(_QWORD *)(a1 + 8) = &ipx::mtf::MtfTransportServerCoreUI::`vftable'{for `ipx::mtf::IMtfTransportServerPrivate'};
  *(_QWORD *)(a1 + 16) = &ipx::mtf::MtfTransportServerCoreUI::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfTransportSynchronousExtenstion,void,void,void,void>'};
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_QWORD *)(a1 + 80) = 0;
  *(_WORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = 2;
  *(_QWORD *)(a1 + 168) = 7;
  *(_QWORD *)(a1 + 160) = 0;
  *(_WORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 2;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 208) = a2;
  *(_DWORD *)(a1 + 212) = a2 & 0xF;
  *(_DWORD *)(a1 + 216) = a2 & 0xF0;
  *(_DWORD *)(a1 + 220) = a2 & 0xF00;
  *(_WORD *)(a1 + 224) = 0;
  *(_BYTE *)(a1 + 226) = 0;
  *(_QWORD *)(a1 + 232) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 264) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_CLIENT_KEY const,RefPtr<ipx::mtf::MtfTransportClientCoreUI>>>>::_Buyheadnode();
  _InterlockedIncrement(&g_cRefDll);
  if ( *(_DWORD *)(a1 + 212) == 1 )
  {
    v15 = *(_DWORD *)(a1 + 220);
    if ( v15 == 256 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2CA,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        v5);
    *(_WORD *)(a1 + 224) = 256;
    if ( *(_DWORD *)(a1 + 216) == 32 )
    {
      v16 = L"System\\MTFQueueEndpointOP";
      if ( v15 != 512 )
        v16 = L"System\\MTFQueueEndpoint";
      GetDesktopUniqueName(v16, Src, v4);
      v23[0] = off_1800316B0;
      v23[1] = a1;
      v24 = v23;
      v17 = ipx::mtf::CoreUIMessageListener::Initialize(a1 + 32, 1, Src, (__int64)v23);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2DF,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v17,
          v22);
      v18 = v24;
      if ( v24 )
      {
        v19 = v23;
        LOBYTE(v19) = v24 != v23;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v19);
        v18 = 0;
        v24 = 0;
      }
      if ( v18 )
      {
        v20 = v23;
        LOBYTE(v20) = v18 != v23;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v18 + 32LL))(v18, v20);
      }
    }
  }
  else if ( *(_DWORD *)(a1 + 212) == 2 )
  {
    *(_BYTE *)(a1 + 224) = *(_DWORD *)(a1 + 220) != 256;
    *(_BYTE *)(a1 + 225) = 0;
    v6 = operator new(0x40u);
    v8 = v6;
    if ( v6 )
    {
      v6[2] = 0;
      *(_QWORD *)v6 = &ipx::mtf::SharedData::`vftable';
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 5) = 0;
      *((_QWORD *)v6 + 6) = 0;
      v6[14] = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      v10 = (void *)*((_QWORD *)v8 + 5);
      if ( v10 )
        CloseHandle(v10);
      *((_QWORD *)v8 + 5) = EventW;
      *((_QWORD *)v8 + 3) = 0;
      v8[8] = 0;
      if ( v8 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    else
    {
      v8 = 0;
    }
    v11 = *(_QWORD *)(a1 + 200);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *(_QWORD *)(a1 + 200) = v8;
    v12 = *(_DWORD *)(a1 + 220);
    if ( v12 != 256 && *(_DWORD *)(a1 + 216) == 32 )
    {
      v13 = L"System\\MTFQueueEndpointOP";
      if ( v12 != 512 )
        v13 = L"System\\MTFQueueEndpoint";
      GetDesktopUniqueName(v13, Src, v7);
      *(_QWORD *)(a1 + 192) = 1;
      if ( Src[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( Src[v14] );
      }
      std::wstring::assign((void *)(a1 + 144), Src);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001ed80  push    rbp
0x18001ed82  push    rbx
0x18001ed83  push    rdi
0x18001ed84  push    r12
0x18001ed86  push    r14
0x18001ed88  push    r15
0x18001ed8a  lea     rbp, [rsp-178h]
0x18001ed92  sub     rsp, 278h
0x18001ed99  mov     rax, cs:__security_cookie
0x18001eda0  xor     rax, rsp
0x18001eda3  mov     [rbp+1A0h+var_40], rax
0x18001edaa  mov     rdi, rcx
0x18001edad  mov     [rsp+2A0h+var_278], rcx
0x18001edb2  xor     r12d, r12d
0x18001edb5  mov     [rcx+18h], r12d
0x18001edb9  lea     rax, ??_7MtfTransportServerCoreUI@mtf@ipx@@6B@; const ipx::mtf::MtfTransportServerCoreUI::`vftable'
0x18001edc0  mov     [rcx], rax
0x18001edc3  lea     rax, ??_7MtfTransportServerCoreUI@mtf@ipx@@6BIMtfTransportServerPrivate@12@@; const ipx::mtf::MtfTransportServerCoreUI::`vftable'{for `ipx::mtf::IMtfTransportServerPrivate'}
0x18001edca  mov     [rcx+8], rax
0x18001edce  lea     rax, ??_7MtfTransportServerCoreUI@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfTransportSynchronousExtenstion@@XXXX@@@; const ipx::mtf::MtfTransportServerCoreUI::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfTransportSynchronousExtenstion,void,void,void,void>'}
0x18001edd5  mov     [rcx+10h], rax
0x18001edd9  mov     [rcx+38h], r12
0x18001eddd  lea     r9d, [r12+7]
0x18001ede2  mov     [rcx+58h], r9
0x18001ede6  mov     [rcx+50h], r12
0x18001edea  mov     [rcx+40h], r12w
0x18001edef  mov     [rcx+60h], r12
0x18001edf3  mov     [rcx+68h], r12
0x18001edf7  mov     [rcx+70h], r12
0x18001edfb  mov     [rcx+78h], r12
0x18001edff  lea     ecx, [r12+2]
0x18001ee04  mov     [rdi+80h], ecx
0x18001ee0a  lea     r15, [rdi+90h]
0x18001ee11  mov     [r15+18h], r9
0x18001ee15  mov     [r15+10h], r12
0x18001ee19  mov     [r15], r12w
0x18001ee1d  mov     [rdi+0B0h], r12
0x18001ee24  mov     [rdi+0B8h], r12
0x18001ee2b  mov     qword ptr [rdi+0C0h], 2
0x18001ee36  mov     [rdi+0C8h], r12
0x18001ee3d  mov     [rdi+0D0h], edx
0x18001ee43  mov     eax, edx
0x18001ee45  and     eax, 0Fh
0x18001ee48  mov     [rdi+0D4h], eax
0x18001ee4e  mov     eax, edx
0x18001ee50  and     eax, 0F0h
0x18001ee55  mov     [rdi+0D8h], eax
0x18001ee5b  and     edx, 0F00h
0x18001ee61  mov     [rdi+0DCh], edx
0x18001ee67  mov     [rdi+0E0h], r12w
0x18001ee6f  mov     [rdi+0E2h], r12b
0x18001ee76  mov     [rdi+0E8h], r8
0x18001ee7d  test    r8, r8
0x18001ee80  jz      short loc_18001EE92
0x18001ee82  mov     rax, [r8]
0x18001ee85  mov     rcx, r8
0x18001ee88  mov     rax, [rax+8]
0x18001ee8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee91  nop
0x18001ee92  mov     [rdi+0F0h], r12
0x18001ee99  lea     rbx, [rdi+108h]
0x18001eea0  mov     [rbx], r12
0x18001eea3  mov     [rbx+8], r12
0x18001eea7  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@V?$allocator@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_CLIENT_KEY@@V?$RefPtr@VMtfTransportClientCoreUI@mtf@ipx@@@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_CLIENT_KEY const,RefPtr<ipx::mtf::MtfTransportClientCoreUI>>>>::_Buyheadnode(void)
0x18001eeac  mov     [rbx], rax
0x18001eeaf  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x18001eeb6  mov     ecx, [rdi+0D4h]
0x18001eebc  sub     ecx, 1
0x18001eebf  jz      loc_18001F004
0x18001eec5  cmp     ecx, 1
0x18001eec8  jnz     loc_18001F0DA
0x18001eece  cmp     dword ptr [rdi+0DCh], 100h
0x18001eed8  setnz   al
0x18001eedb  mov     [rdi+0E0h], al
0x18001eee1  mov     [rdi+0E1h], r12b
0x18001eee8  mov     ecx, 40h ; '@'; Size
0x18001eeed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eef2  mov     rbx, rax
0x18001eef5  mov     [rsp+2A0h+var_280], rax
0x18001eefa  test    rax, rax
0x18001eefd  jz      short loc_18001EF64
0x18001eeff  mov     [rax+8], r12d
0x18001ef03  lea     rax, ??_7SharedData@mtf@ipx@@6B@; const ipx::mtf::SharedData::`vftable'
0x18001ef0a  mov     [rbx], rax
0x18001ef0d  xor     eax, eax
0x18001ef0f  mov     [rbx+10h], rax
0x18001ef13  mov     [rbx+28h], r12
0x18001ef17  mov     [rbx+30h], r12
0x18001ef1b  mov     [rbx+38h], r12d
0x18001ef1f  xor     r9d, r9d; lpName
0x18001ef22  xor     r8d, r8d; bInitialState
0x18001ef25  xor     edx, edx; bManualReset
0x18001ef27  xor     ecx, ecx; lpEventAttributes
0x18001ef29  call    cs:__imp_CreateEventW
0x18001ef2f  mov     r14, rax
0x18001ef32  mov     rcx, [rbx+28h]; hObject
0x18001ef36  test    rcx, rcx
0x18001ef39  jz      short loc_18001EF41
0x18001ef3b  call    cs:__imp_CloseHandle
0x18001ef41  mov     [rbx+28h], r14
0x18001ef45  xor     eax, eax
0x18001ef47  mov     [rbx+18h], rax
0x18001ef4b  mov     [rbx+20h], eax
0x18001ef4e  test    rbx, rbx
0x18001ef51  jz      short loc_18001EF67
0x18001ef53  mov     rax, [rbx]
0x18001ef56  mov     rcx, rbx
0x18001ef59  mov     rax, [rax+8]
0x18001ef5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef62  jmp     short loc_18001EF67
0x18001ef64  mov     rbx, r12
0x18001ef67  mov     rcx, [rdi+0C8h]
0x18001ef6e  test    rcx, rcx
0x18001ef71  jz      short loc_18001EF7F
0x18001ef73  mov     rax, [rcx]
0x18001ef76  mov     rax, [rax+10h]
0x18001ef7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef7f  mov     [rdi+0C8h], rbx
0x18001ef86  mov     edx, [rdi+0DCh]
0x18001ef8c  cmp     edx, 100h
0x18001ef92  jz      loc_18001F0DA
0x18001ef98  cmp     dword ptr [rdi+0D8h], 20h ; ' '
0x18001ef9f  jnz     loc_18001F0DA
0x18001efa5  lea     rax, aSystemMtfqueue; "System\\MTFQueueEndpoint"
0x18001efac  lea     rcx, aSystemMtfqueue_0; "System\\MTFQueueEndpointOP"
0x18001efb3  cmp     edx, 200h
0x18001efb9  cmovnz  rcx, rax; unsigned __int16 *
0x18001efbd  lea     rdx, [rsp+2A0h+Src]; unsigned __int16 *
0x18001efc2  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x18001efc7  mov     qword ptr [rdi+0C0h], 1
0x18001efd2  cmp     [rsp+2A0h+Src], r12w
0x18001efd8  jnz     short loc_18001EFDF
0x18001efda  mov     r8, r12
0x18001efdd  jmp     short loc_18001EFF2
0x18001efdf  lea     rax, [rsp+2A0h+Src]
0x18001efe4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001efe8  inc     r8
0x18001efeb  cmp     [rax+r8*2], r12w
0x18001eff0  jnz     short loc_18001EFE8
0x18001eff2  lea     rdx, [rsp+2A0h+Src]; Src
0x18001eff7  mov     rcx, r15; void *
0x18001effa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001efff  jmp     loc_18001F0DA
0x18001f004  mov     edx, [rdi+0DCh]
0x18001f00a  mov     rcx, [rbp+1A8h]; this
0x18001f011  cmp     edx, 100h
0x18001f017  jz      loc_18001F112
0x18001f01d  mov     word ptr [rdi+0E0h], 100h
0x18001f026  cmp     dword ptr [rdi+0D8h], 20h ; ' '
0x18001f02d  jnz     loc_18001F0DA
0x18001f033  lea     rax, aSystemMtfqueue; "System\\MTFQueueEndpoint"
0x18001f03a  lea     rcx, aSystemMtfqueue_0; "System\\MTFQueueEndpointOP"
0x18001f041  cmp     edx, 200h
0x18001f047  cmovnz  rcx, rax; unsigned __int16 *
0x18001f04b  lea     rdx, [rsp+2A0h+Src]; unsigned __int16 *
0x18001f050  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x18001f055  nop
0x18001f056  lea     rax, off_1800316B0
0x18001f05d  mov     [rsp+2A0h+var_270], rax
0x18001f062  mov     [rsp+2A0h+var_268], rdi
0x18001f067  lea     rax, [rsp+2A0h+var_270]
0x18001f06c  mov     [rsp+2A0h+var_258], rax
0x18001f071  lea     r9, [rsp+2A0h+var_270]
0x18001f076  lea     r8, [rsp+2A0h+Src]
0x18001f07b  mov     edx, 1
0x18001f080  lea     rcx, [rdi+20h]
0x18001f084  call    ?Initialize@CoreUIMessageListener@mtf@ipx@@QEAAJIPEBGAEBV?$function@$$A6AJPEBXH@Z@std@@@Z; ipx::mtf::CoreUIMessageListener::Initialize(uint,ushort const *,std::function<long (void const *,int)> const &)
0x18001f089  mov     rcx, [rbp+1A8h]; this
0x18001f090  test    eax, eax
0x18001f092  js      short loc_18001F0FD
0x18001f094  mov     rcx, [rsp+2A0h+var_258]
0x18001f099  test    rcx, rcx
0x18001f09c  jz      short loc_18001F0BD
0x18001f09e  mov     rax, [rcx]
0x18001f0a1  lea     rdx, [rsp+2A0h+var_270]
0x18001f0a6  cmp     rcx, rdx
0x18001f0a9  setnz   dl
0x18001f0ac  mov     rax, [rax+20h]
0x18001f0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b5  mov     rcx, r12
0x18001f0b8  mov     [rsp+2A0h+var_258], rcx
0x18001f0bd  test    rcx, rcx
0x18001f0c0  jz      short loc_18001F0DA
0x18001f0c2  mov     rax, [rcx]
0x18001f0c5  lea     rdx, [rsp+2A0h+var_270]
0x18001f0ca  cmp     rcx, rdx
0x18001f0cd  setnz   dl
0x18001f0d0  mov     rax, [rax+20h]
0x18001f0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0d9  nop
0x18001f0da  mov     rax, rdi
0x18001f0dd  mov     rcx, [rbp+1A0h+var_40]
0x18001f0e4  xor     rcx, rsp; StackCookie
0x18001f0e7  call    __security_check_cookie
0x18001f0ec  add     rsp, 278h
0x18001f0f3  pop     r15
0x18001f0f5  pop     r14
0x18001f0f7  pop     r12
0x18001f0f9  pop     rdi
0x18001f0fa  pop     rbx
0x18001f0fb  pop     rbp
0x18001f0fc  retn
0x18001f0fd  mov     r9d, eax; char *
0x18001f100  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18001f107  mov     edx, 2DFh; void *
0x18001f10c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f112  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18001f119  mov     edx, 2CAh; void *
0x18001f11e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
