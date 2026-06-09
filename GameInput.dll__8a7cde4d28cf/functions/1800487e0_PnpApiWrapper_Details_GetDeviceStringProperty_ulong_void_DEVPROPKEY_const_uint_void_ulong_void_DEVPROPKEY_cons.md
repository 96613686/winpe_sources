# PnpApiWrapper::Details::GetDeviceStringProperty(ulong (*)(void *,_DEVPROPKEY const *,uint &,void *,ulong *),void *,_DEVPROPKEY const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)

- ea: `0x1800487e0`
- end: `0x180048b7d`
- name: `?GetDeviceStringProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@AEAI0PEAK@Z01AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z`
- size: `925`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180030308`
- `0x1800484f0`
- `0x1800485a8`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x180047d74`
- `0x1800487e0`
- `0x18004c8a5`
- `0x18004d010`

## import_xrefs

- `ntdll!wcsnlen` at `0x180048a6f`
- `ntdll!wcsnlen` at `0x180048a6f`
- `ntdll!RtlAllocateHeap` at `0x180048919`
- `ntdll!RtlAllocateHeap` at `0x180048919`

## pseudocode

```c
__int64 __fastcall PnpApiWrapper::Details::GetDeviceStringProperty(
        __int64 (__fastcall *a1)(const struct std::nothrow_t *, __int64, unsigned int *, _WORD *, int *),
        const struct std::nothrow_t *a2,
        __int64 a3,
        void **a4)
{
  void *v5; // rcx
  unsigned int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // esi
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v16; // rdi
  SIZE_T v17; // rax
  _WORD *Heap; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  _WORD *v21; // rbx
  unsigned int v22; // eax
  unsigned int v23; // edx
  int v24; // eax
  const struct std::nothrow_t *v25; // rdx
  __int16 *v26; // r8
  __int64 v27; // r9
  unsigned int v28; // r15d
  size_t v29; // rcx
  __int16 v30; // ax
  void *v31; // rcx
  int v32; // [rsp+40h] [rbp-10h] BYREF
  int v33; // [rsp+44h] [rbp-Ch] BYREF
  const char *v34; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v35; // [rsp+90h] [rbp+40h] BYREF
  int v36; // [rsp+A8h] [rbp+58h] BYREF

  v5 = *a4;
  *a4 = 0;
  if ( v5 )
    operator delete(v5, a2);
  v36 = 0;
  v35 = 0;
  v9 = a1(a2, a3, &v35, 0, &v36);
  v11 = -2088054781;
  if ( v9 && v9 != 26 )
  {
    if ( v9 == 37 )
      return 1;
    v12 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)v9, v10);
    if ( v12 == -2088054781 )
      return v11;
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x200) != 0
        && (qword_180069018 & 0x200) == qword_180069018 )
      {
        v32 = v12;
        v34 = "onecore\\xbox\\gameinput\\providers\\PnpApiWrapper.cpp";
        v33 = 402;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          512,
          (unsigned __int8 *)byte_180063B1B,
          v13,
          v14,
          (__int64 **)&v34,
          (__int64)&v33,
          (__int64)&v32);
      }
      return (unsigned int)v12;
    }
  }
  if ( v35 <= 2 )
    return 1;
  v16 = ((unsigned __int64)v35 + 1) >> 1;
  v17 = 2 * v16;
  if ( !is_mul_ok(v16, 2u) )
    v17 = -1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  v21 = Heap;
  if ( !Heap )
  {
    v12 = -2147024882;
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x200) != 0
      && (qword_180069018 & 0x200) == qword_180069018 )
    {
      v33 = -2147024882;
      v32 = 420;
      v34 = "onecore\\xbox\\gameinput\\providers\\PnpApiWrapper.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&v34,
        (unsigned __int8 *)&unk_180063DE0,
        v19,
        v20,
        (__int64 **)&v34,
        (__int64)&v32,
        (__int64)&v33);
    }
    return (unsigned int)v12;
  }
  memset_0(Heap, 0, 2 * v16);
  v22 = a1(a2, a3, &v35, v21, &v36);
  v24 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)v22, v23);
  v28 = v24;
  if ( v24 == -2088054781 )
  {
LABEL_29:
    operator delete(v21, v25);
    return v11;
  }
  v25 = 0;
  if ( v24 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v25 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 0x200) != 0 && (qword_180069018 & 0x200) == qword_180069018 )
      {
        v33 = v24;
        v34 = "onecore\\xbox\\gameinput\\providers\\PnpApiWrapper.cpp";
        v32 = 430;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          512,
          (unsigned __int8 *)byte_180063EE7,
          (__int64)v26,
          v27,
          (__int64 **)&v34,
          (__int64)&v32,
          (__int64)&v33);
      }
    }
    v11 = v28;
    goto LABEL_29;
  }
  if ( v16 )
  {
    v26 = v21;
    if ( v36 == 18 )
    {
      v29 = wcsnlen(v21, v16);
      goto LABEL_41;
    }
    if ( v36 == 8210 && *v21 )
    {
      v29 = 1;
      if ( v16 <= 1 )
        goto LABEL_42;
      while ( 1 )
      {
        v30 = *v26++;
        if ( !v30 && !*v26 )
          goto LABEL_47;
        if ( ++v29 >= v16 )
          goto LABEL_42;
      }
    }
  }
  v29 = 0;
LABEL_41:
  if ( v29 >= v16 )
  {
LABEL_42:
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v25 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 0x200) != 0 && (qword_180069018 & 0x200) == qword_180069018 )
      {
        v33 = -2088054783;
        v34 = "onecore\\xbox\\gameinput\\providers\\PnpApiWrapper.cpp";
        v32 = 435;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          512,
          (unsigned __int8 *)word_180063C22,
          (__int64)v26,
          v27,
          (__int64 **)&v34,
          (__int64)&v32,
          (__int64)&v33);
      }
    }
    operator delete(v21, v25);
    return 2206912513LL;
  }
LABEL_47:
  if ( !v29 )
  {
    operator delete(v21, v25);
    return 1;
  }
  v31 = *a4;
  *a4 = v21;
  if ( v31 )
    operator delete(v31, v25);
  return 0;
}

```

## disassembly

```asm
0x1800487e0  mov     [rsp-38h+arg_8], rbx
0x1800487e5  push    rbp
0x1800487e6  push    rsi
0x1800487e7  push    rdi
0x1800487e8  push    r12
0x1800487ea  push    r13
0x1800487ec  push    r14
0x1800487ee  push    r15
0x1800487f0  mov     rbp, rsp
0x1800487f3  sub     rsp, 50h
0x1800487f7  xor     edi, edi
0x1800487f9  mov     r13, rcx
0x1800487fc  mov     rcx, [r9]; P
0x1800487ff  mov     r14, r9
0x180048802  mov     [r9], rdi
0x180048805  mov     r15, r8
0x180048808  mov     r12, rdx
0x18004880b  test    rcx, rcx
0x18004880e  jz      short loc_180048815
0x180048810  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048815  lea     rax, [rbp+arg_18]
0x180048819  mov     [rbp+arg_18], edi
0x18004881c  mov     [rsp+50h+var_30], rax
0x180048821  lea     r8, [rbp+arg_0]
0x180048825  mov     rax, r13
0x180048828  mov     [rbp+arg_0], edi
0x18004882b  xor     r9d, r9d
0x18004882e  mov     rdx, r15
0x180048831  mov     rcx, r12
0x180048834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048839  mov     esi, 838AD003h
0x18004883e  test    eax, eax
0x180048840  jz      loc_1800488E1
0x180048846  cmp     eax, 1Ah
0x180048849  jz      loc_1800488E1
0x18004884f  cmp     eax, 25h ; '%'
0x180048852  jz      loc_180048B5F
0x180048858  mov     ecx, eax; this
0x18004885a  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x18004885f  mov     ebx, eax
0x180048861  cmp     eax, esi
0x180048863  jnz     short loc_18004886C
0x180048865  mov     eax, esi
0x180048867  jmp     loc_180048B64
0x18004886c  test    ebx, ebx
0x18004886e  jns     short loc_1800488E1
0x180048870  mov     eax, cs:dword_180069000
0x180048876  cmp     eax, 2
0x180048879  jbe     short loc_1800488DA
0x18004887b  mov     rdx, cs:qword_180069018
0x180048882  mov     ecx, 200h
0x180048887  mov     rax, cs:qword_180069010
0x18004888e  test    rcx, rax
0x180048891  jz      short loc_1800488DA
0x180048893  mov     rax, rdx
0x180048896  and     rax, rcx
0x180048899  cmp     rax, rdx
0x18004889c  jnz     short loc_1800488DA
0x18004889e  lea     rax, aOnecoreXboxGam_39; "onecore\\xbox\\gameinput\\providers\\Pn"...
0x1800488a5  mov     [rbp+var_10], ebx
0x1800488a8  mov     [rbp+var_8], rax
0x1800488ac  lea     rdx, byte_180063B1B
0x1800488b3  lea     rax, [rbp+var_10]
0x1800488b7  mov     [rbp+var_C], 192h
0x1800488be  mov     [rsp+50h+var_20], rax
0x1800488c3  lea     rax, [rbp+var_C]
0x1800488c7  mov     [rsp+50h+var_28], rax
0x1800488cc  lea     rax, [rbp+var_8]
0x1800488d0  mov     [rsp+50h+var_30], rax
0x1800488d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800488da  mov     eax, ebx
0x1800488dc  jmp     loc_180048B64
0x1800488e1  cmp     [rbp+arg_0], 2
0x1800488e5  jbe     loc_180048B5F
0x1800488eb  mov     edi, [rbp+arg_0]
0x1800488ee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800488f5  inc     rdi
0x1800488f8  mov     eax, 2
0x1800488fd  shr     rdi, 1
0x180048900  mul     rdi
0x180048903  cmovb   rax, rcx
0x180048907  mov     rcx, gs:60h
0x180048910  mov     r8, rax; Size
0x180048913  xor     edx, edx; Flags
0x180048915  mov     rcx, [rcx+30h]; HeapHandle
0x180048919  call    cs:__imp_RtlAllocateHeap
0x180048920  nop     dword ptr [rax+rax+00h]
0x180048925  mov     rbx, rax
0x180048928  test    rax, rax
0x18004892b  jnz     short loc_1800489A0
0x18004892d  mov     eax, cs:dword_180069000
0x180048933  mov     ebx, 8007000Eh
0x180048938  cmp     eax, 2
0x18004893b  jbe     short loc_1800488DA
0x18004893d  mov     rdx, cs:qword_180069018
0x180048944  mov     ecx, 200h
0x180048949  mov     rax, cs:qword_180069010
0x180048950  test    rcx, rax
0x180048953  jz      short loc_1800488DA
0x180048955  mov     rax, rdx
0x180048958  and     rax, rcx
0x18004895b  cmp     rax, rdx
0x18004895e  jnz     loc_1800488DA
0x180048964  lea     rcx, [rbp+var_C]
0x180048968  mov     [rbp+var_C], ebx
0x18004896b  mov     [rsp+50h+var_20], rcx
0x180048970  lea     rax, aOnecoreXboxGam_39; "onecore\\xbox\\gameinput\\providers\\Pn"...
0x180048977  lea     rcx, [rbp+var_10]
0x18004897b  mov     [rbp+var_10], 1A4h
0x180048982  mov     [rsp+50h+var_28], rcx
0x180048987  lea     rdx, unk_180063DE0
0x18004898e  lea     rcx, [rbp+var_8]
0x180048992  mov     [rbp+var_8], rax
0x180048996  mov     [rsp+50h+var_30], rcx
0x18004899b  jmp     loc_1800488D5
0x1800489a0  lea     r8, [rdi+rdi]; Size
0x1800489a4  xor     edx, edx; Val
0x1800489a6  mov     rcx, rbx; void *
0x1800489a9  call    memset_0
0x1800489ae  lea     rax, [rbp+arg_18]
0x1800489b2  mov     r9, rbx
0x1800489b5  mov     [rsp+50h+var_30], rax
0x1800489ba  lea     r8, [rbp+arg_0]
0x1800489be  mov     rax, r13
0x1800489c1  mov     rdx, r15
0x1800489c4  mov     rcx, r12
0x1800489c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489cc  mov     ecx, eax; this
0x1800489ce  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x1800489d3  mov     r15d, eax
0x1800489d6  cmp     eax, esi
0x1800489d8  jz      short loc_180048A4E
0x1800489da  xor     edx, edx; struct std::nothrow_t *
0x1800489dc  test    eax, eax
0x1800489de  jns     short loc_180048A5B
0x1800489e0  mov     eax, cs:dword_180069000
0x1800489e6  cmp     eax, 2
0x1800489e9  jbe     short loc_180048A4B
0x1800489eb  mov     rdx, cs:qword_180069018
0x1800489f2  mov     ecx, 200h
0x1800489f7  mov     rax, cs:qword_180069010
0x1800489fe  test    rcx, rax
0x180048a01  jz      short loc_180048A4B
0x180048a03  mov     rax, rdx
0x180048a06  and     rax, rcx
0x180048a09  cmp     rax, rdx
0x180048a0c  jnz     short loc_180048A4B
0x180048a0e  lea     rax, aOnecoreXboxGam_39; "onecore\\xbox\\gameinput\\providers\\Pn"...
0x180048a15  mov     [rbp+var_C], r15d
0x180048a19  mov     [rbp+var_8], rax
0x180048a1d  lea     rdx, byte_180063EE7
0x180048a24  lea     rax, [rbp+var_C]
0x180048a28  mov     [rbp+var_10], 1AEh
0x180048a2f  mov     [rsp+50h+var_20], rax
0x180048a34  lea     rax, [rbp+var_10]
0x180048a38  mov     [rsp+50h+var_28], rax
0x180048a3d  lea     rax, [rbp+var_8]
0x180048a41  mov     [rsp+50h+var_30], rax
0x180048a46  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048a4b  mov     esi, r15d
0x180048a4e  mov     rcx, rbx; P
0x180048a51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048a56  jmp     loc_180048865
0x180048a5b  test    rdi, rdi
0x180048a5e  jz      short loc_180048AB9
0x180048a60  cmp     [rbp+arg_18], 12h
0x180048a64  mov     r8, rbx
0x180048a67  jnz     short loc_180048A80
0x180048a69  mov     rdx, rdi; MaxCount
0x180048a6c  mov     rcx, rbx; Source
0x180048a6f  call    cs:__imp_wcsnlen
0x180048a76  nop     dword ptr [rax+rax+00h]
0x180048a7b  mov     rcx, rax
0x180048a7e  jmp     short loc_180048ABC
0x180048a80  cmp     [rbp+arg_18], 2012h
0x180048a87  jnz     short loc_180048AB9
0x180048a89  cmp     [rbx], dx
0x180048a8c  jz      short loc_180048AB9
0x180048a8e  mov     ecx, 1
0x180048a93  cmp     rdi, rcx
0x180048a96  jbe     short loc_180048AC1
0x180048a98  movzx   eax, word ptr [r8]
0x180048a9c  lea     r8, [r8+2]
0x180048aa0  test    ax, ax
0x180048aa3  jnz     short loc_180048AAF
0x180048aa5  cmp     [r8], dx
0x180048aa9  jz      loc_180048B3E
0x180048aaf  inc     rcx
0x180048ab2  cmp     rcx, rdi
0x180048ab5  jb      short loc_180048A98
0x180048ab7  jmp     short loc_180048AC1
0x180048ab9  mov     rcx, rdx
0x180048abc  cmp     rcx, rdi
0x180048abf  jb      short loc_180048B3E
0x180048ac1  mov     eax, cs:dword_180069000
0x180048ac7  cmp     eax, 2
0x180048aca  jbe     short loc_180048B2F
0x180048acc  mov     rdx, cs:qword_180069018
0x180048ad3  mov     ecx, 200h
0x180048ad8  mov     rax, cs:qword_180069010
0x180048adf  test    rcx, rax
0x180048ae2  jz      short loc_180048B2F
0x180048ae4  mov     rax, rdx
0x180048ae7  and     rax, rcx
0x180048aea  cmp     rax, rdx
0x180048aed  jnz     short loc_180048B2F
0x180048aef  lea     rax, aOnecoreXboxGam_39; "onecore\\xbox\\gameinput\\providers\\Pn"...
0x180048af6  mov     [rbp+var_C], 838AD001h
0x180048afd  mov     [rbp+var_8], rax
0x180048b01  lea     rdx, word_180063C22
0x180048b08  lea     rax, [rbp+var_C]
0x180048b0c  mov     [rbp+var_10], 1B3h
0x180048b13  mov     [rsp+50h+var_20], rax
0x180048b18  lea     rax, [rbp+var_10]
0x180048b1c  mov     [rsp+50h+var_28], rax
0x180048b21  lea     rax, [rbp+var_8]
0x180048b25  mov     [rsp+50h+var_30], rax
0x180048b2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048b2f  mov     rcx, rbx; P
0x180048b32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048b37  mov     eax, 838AD001h
0x180048b3c  jmp     short loc_180048B64
0x180048b3e  test    rcx, rcx
0x180048b41  jz      short loc_180048B57
0x180048b43  mov     rcx, [r14]; P
0x180048b46  mov     [r14], rbx
0x180048b49  test    rcx, rcx
0x180048b4c  jz      short loc_180048B53
0x180048b4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048b53  xor     eax, eax
0x180048b55  jmp     short loc_180048B64
0x180048b57  mov     rcx, rbx; P
0x180048b5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048b5f  mov     eax, 1
0x180048b64  mov     rbx, [rsp+50h+arg_8]
0x180048b6c  add     rsp, 50h
0x180048b70  pop     r15
0x180048b72  pop     r14
0x180048b74  pop     r13
0x180048b76  pop     r12
0x180048b78  pop     rdi
0x180048b79  pop     rsi
0x180048b7a  pop     rbp
0x180048b7b  retn
```
