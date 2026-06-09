# CCompositeSystemEffect::GetEffectsList(_GUID * *,uint *,void *)

- ea: `0x1800567c0`
- end: `0x180056a81`
- name: `?GetEffectsList@CCompositeSystemEffect@@UEAAJPEAPEAU_GUID@@PEAIPEAX@Z`
- size: `705`
- prototype: `__int64 __fastcall(CCompositeSystemEffect *__hidden this, struct _GUID **, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800126bc`
- `0x1800567c0`
- `0x180056a88`
- `0x18006e630`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180056898`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800568ee`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180056898`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800568ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056955`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056963`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056995`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800569a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056a53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056a61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056955`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056963`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056995`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800569a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056a53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056a61`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056a2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005697f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005697f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800569fb`

## string_xrefs

- `0x180056939`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`

## pseudocode

```c
__int64 __fastcall CCompositeSystemEffect::GetEffectsList(
        CCompositeSystemEffect *this,
        struct _GUID **a2,
        unsigned int *a3,
        void *a4)
{
  CCompositeSystemEffect *v5; // r8
  void *v6; // rbx
  char *v7; // rdi
  int v8; // r15d
  unsigned int v9; // r13d
  char *v10; // rsi
  int v11; // r12d
  __int64 v12; // rbp
  unsigned int i; // r14d
  _QWORD *v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  __int64 v18; // rax
  char *v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // rax
  char *v22; // rcx
  __int64 v24; // rbp
  struct _GUID *v25; // r13
  __int64 v26; // rcx
  int v27; // r14d
  void *v28; // rbx
  int v29; // [rsp+20h] [rbp-88h]
  int v30; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v31; // [rsp+34h] [rbp-74h]
  unsigned int v32; // [rsp+38h] [rbp-70h]
  __int64 v33; // [rsp+40h] [rbp-68h] BYREF
  __int64 v34; // [rsp+48h] [rbp-60h]
  __int64 v35; // [rsp+50h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = this;
  v6 = a4;
  if ( !a2 || !a3 )
    return 2147500035LL;
  v7 = 0;
  v8 = 0;
  *a2 = 0;
  v9 = 0;
  *a3 = 0;
  v10 = 0;
  v31 = 0;
  v11 = 0;
  v12 = 0;
  for ( i = 0; ; ++i )
  {
    v32 = v12;
    if ( (signed int)i >= *((_DWORD *)v5 + 30) )
      break;
    v33 = 0;
    v30 = 0;
    v14 = (_QWORD *)ATL::CSimpleArray<HINSTANCE__ *,ATL::CSimpleArrayEqualHelper<HINSTANCE__ *>>::operator[](
                      (char *)v5 + 112,
                      i);
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, int *, void *))(*(_QWORD *)*v14 + 24LL))(*v14, &v33, &v30, v6);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CB,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\systemeffect.cpp",
        (const char *)(unsigned int)v15,
        v29);
      if ( v10 )
        free(v10);
      if ( v7 )
        free(v7);
      return v16;
    }
    if ( v8 != v9 )
      goto LABEL_13;
    if ( v9 )
    {
      v17 = 2 * v8;
      if ( (v8 & 0x40000000) != 0 )
        goto LABEL_16;
    }
    else
    {
      v17 = 1;
    }
    if ( v17 <= 0xFFFFFFFuLL )
    {
      v18 = _o__recalloc(v7, v17, 8);
      if ( v18 )
      {
        v9 = v17;
        v7 = (char *)v18;
LABEL_13:
        v19 = &v7[8 * v8];
        if ( v19 )
          *(_QWORD *)v19 = v33;
        ++v8;
      }
    }
LABEL_16:
    if ( v11 != v31 )
      goto LABEL_23;
    if ( v31 )
    {
      v20 = 2 * v11;
      if ( (v11 & 0x40000000) != 0 )
        goto LABEL_26;
    }
    else
    {
      v20 = 1;
    }
    if ( v20 <= 0x1FFFFFFFuLL )
    {
      v21 = _o__recalloc(v10, v20, 4);
      if ( v21 )
      {
        v31 = v20;
        v10 = (char *)v21;
LABEL_23:
        v22 = &v10[4 * v11];
        if ( v22 )
          *(_DWORD *)v22 = v30;
        ++v11;
      }
    }
LABEL_26:
    v12 = (unsigned int)(v30 + v12);
    v5 = this;
    v6 = a4;
  }
  if ( (_DWORD)v12 )
  {
    v24 = 16 * v12;
    v25 = (struct _GUID *)CoTaskMemAlloc(v24);
    if ( !v25 )
    {
      if ( v10 )
        free(v10);
      if ( v7 )
        free(v7);
      return 2147942414LL;
    }
    v26 = 0;
    v27 = 0;
    v31 = 0;
    if ( v8 > 0 )
    {
      while ( 1 )
      {
        if ( v27 < 0 || v27 >= v11 )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          __debugbreak();
        }
        v28 = *(void **)&v7[8 * v27];
        v35 = *(unsigned int *)&v10[4 * v27];
        v34 = 16 * v35;
        memcpy_s_0(&v25[v26], v24, v28, 16 * v35);
        CoTaskMemFree(v28);
        if ( ++v27 >= v8 )
          break;
        v24 -= v34;
        v26 = (unsigned int)v35 + v31;
        v31 += v35;
      }
    }
    *a2 = v25;
    *a3 = v32;
  }
  if ( v10 )
    free(v10);
  if ( v7 )
    free(v7);
  return 0;
}

```

## disassembly

```asm
0x1800567c0  mov     rax, rsp
0x1800567c3  mov     [rax+20h], r9
0x1800567c7  mov     [rax+18h], r8
0x1800567cb  mov     [rax+10h], rdx
0x1800567cf  mov     [rax+8], rcx
0x1800567d3  push    rbx
0x1800567d4  push    rbp
0x1800567d5  push    rsi
0x1800567d6  push    rdi
0x1800567d7  push    r12
0x1800567d9  push    r13
0x1800567db  push    r14
0x1800567dd  push    r15
0x1800567df  sub     rsp, 68h
0x1800567e3  mov     rax, r8
0x1800567e6  mov     r8, rcx
0x1800567e9  mov     rbx, r9
0x1800567ec  test    rdx, rdx
0x1800567ef  jz      loc_180056A6B
0x1800567f5  test    rax, rax
0x1800567f8  jz      loc_180056A6B
0x1800567fe  xor     ecx, ecx
0x180056800  xor     edi, edi
0x180056802  xor     r15d, r15d
0x180056805  mov     [rdx], rcx
0x180056808  xor     r13d, r13d
0x18005680b  mov     [rax], ecx
0x18005680d  xor     esi, esi
0x18005680f  mov     [rsp+0A8h+var_74], ecx
0x180056813  xor     r12d, r12d
0x180056816  xor     ebp, ebp
0x180056818  xor     r14d, r14d
0x18005681b  mov     [rsp+0A8h+var_70], ebp
0x18005681f  cmp     r14d, [r8+78h]
0x180056823  jge     loc_180056970
0x180056829  lea     rcx, [r8+70h]
0x18005682d  mov     [rsp+0A8h+var_68], 0
0x180056836  mov     edx, r14d
0x180056839  mov     [rsp+0A8h+var_78], 0
0x180056841  call    ??A?$CSimpleArray@PEAUHINSTANCE__@@V?$CSimpleArrayEqualHelper@PEAUHINSTANCE__@@@ATL@@@ATL@@QEAAAEAPEAUHINSTANCE__@@H@Z; ATL::CSimpleArray<HINSTANCE__ *,ATL::CSimpleArrayEqualHelper<HINSTANCE__ *>>::operator[](int)
0x180056846  mov     r9, rbx
0x180056849  lea     r8, [rsp+0A8h+var_78]
0x18005684e  lea     rdx, [rsp+0A8h+var_68]
0x180056853  mov     rcx, [rax]
0x180056856  mov     rax, [rcx]
0x180056859  mov     rax, [rax+18h]
0x18005685d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056862  mov     ebx, eax
0x180056864  test    eax, eax
0x180056866  js      loc_180056931
0x18005686c  cmp     r15d, r13d
0x18005686f  jnz     short loc_1800568A9
0x180056871  test    r13d, r13d
0x180056874  jnz     short loc_18005687C
0x180056876  lea     ebx, [r13+1]
0x18005687a  jmp     short loc_180056884
0x18005687c  lea     ebx, [r15+r15]
0x180056880  test    ebx, ebx
0x180056882  js      short loc_1800568C0
0x180056884  mov     edx, ebx
0x180056886  cmp     rdx, 0FFFFFFFh
0x18005688d  ja      short loc_1800568C0
0x18005688f  mov     r8d, 8
0x180056895  mov     rcx, rdi
0x180056898  call    cs:__imp__o__recalloc
0x18005689e  test    rax, rax
0x1800568a1  jz      short loc_1800568C0
0x1800568a3  mov     r13d, ebx
0x1800568a6  mov     rdi, rax
0x1800568a9  movsxd  rax, r15d
0x1800568ac  lea     rcx, [rdi+rax*8]
0x1800568b0  test    rcx, rcx
0x1800568b3  jz      short loc_1800568BD
0x1800568b5  mov     rax, [rsp+0A8h+var_68]
0x1800568ba  mov     [rcx], rax
0x1800568bd  inc     r15d
0x1800568c0  mov     ecx, [rsp+0A8h+var_74]
0x1800568c4  cmp     r12d, ecx
0x1800568c7  jnz     short loc_180056900
0x1800568c9  test    ecx, ecx
0x1800568cb  jnz     short loc_1800568D2
0x1800568cd  lea     ebx, [rcx+1]
0x1800568d0  jmp     short loc_1800568DA
0x1800568d2  lea     ebx, [r12+r12]
0x1800568d6  test    ebx, ebx
0x1800568d8  js      short loc_180056915
0x1800568da  mov     edx, ebx
0x1800568dc  cmp     rdx, 1FFFFFFFh
0x1800568e3  ja      short loc_180056915
0x1800568e5  mov     r8d, 4
0x1800568eb  mov     rcx, rsi
0x1800568ee  call    cs:__imp__o__recalloc
0x1800568f4  test    rax, rax
0x1800568f7  jz      short loc_180056915
0x1800568f9  mov     [rsp+0A8h+var_74], ebx
0x1800568fd  mov     rsi, rax
0x180056900  movsxd  rax, r12d
0x180056903  lea     rcx, [rsi+rax*4]
0x180056907  test    rcx, rcx
0x18005690a  jz      short loc_180056912
0x18005690c  mov     eax, [rsp+0A8h+var_78]
0x180056910  mov     [rcx], eax
0x180056912  inc     r12d
0x180056915  add     ebp, [rsp+0A8h+var_78]
0x180056919  mov     r8, [rsp+0A8h+arg_0]
0x180056921  inc     r14d
0x180056924  mov     rbx, [rsp+0A8h+arg_18]
0x18005692c  jmp     loc_18005681B
0x180056931  mov     rcx, [rsp+0A8h]; this
0x180056939  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x180056940  mov     r9d, ebx; char *
0x180056943  mov     edx, 4CBh; void *
0x180056948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005694d  test    rsi, rsi
0x180056950  jz      short loc_18005695B
0x180056952  mov     rcx, rsi; Block
0x180056955  call    cs:__imp_free
0x18005695b  test    rdi, rdi
0x18005695e  jz      short loc_180056969
0x180056960  mov     rcx, rdi; Block
0x180056963  call    cs:__imp_free
0x180056969  mov     eax, ebx
0x18005696b  jmp     loc_180056A70
0x180056970  test    ebp, ebp
0x180056972  jz      loc_180056A4B
0x180056978  shl     rbp, 4
0x18005697c  mov     rcx, rbp; cb
0x18005697f  call    cs:__imp_CoTaskMemAlloc
0x180056985  mov     r13, rax
0x180056988  test    rax, rax
0x18005698b  jnz     short loc_1800569B3
0x18005698d  test    rsi, rsi
0x180056990  jz      short loc_18005699B
0x180056992  mov     rcx, rsi; Block
0x180056995  call    cs:__imp_free
0x18005699b  test    rdi, rdi
0x18005699e  jz      short loc_1800569A9
0x1800569a0  mov     rcx, rdi; Block
0x1800569a3  call    cs:__imp_free
0x1800569a9  mov     eax, 8007000Eh
0x1800569ae  jmp     loc_180056A70
0x1800569b3  xor     ecx, ecx
0x1800569b5  xor     r14d, r14d
0x1800569b8  mov     [rsp+0A8h+var_74], ecx
0x1800569bc  test    r15d, r15d
0x1800569bf  jle     short loc_180056A32
0x1800569c1  test    r14d, r14d
0x1800569c4  js      short loc_180056A1C
0x1800569c6  cmp     r14d, r12d
0x1800569c9  jge     short loc_180056A1C
0x1800569cb  movsxd  rax, r14d
0x1800569ce  mov     rdx, rbp; DestinationSize
0x1800569d1  shl     rcx, 4
0x1800569d5  add     rcx, r13; Destination
0x1800569d8  mov     rbx, [rdi+rax*8]
0x1800569dc  mov     eax, [rsi+rax*4]
0x1800569df  mov     r8, rbx; Source
0x1800569e2  mov     [rsp+0A8h+var_58], rax
0x1800569e7  shl     rax, 4
0x1800569eb  mov     r9, rax; SourceSize
0x1800569ee  mov     [rsp+0A8h+var_60], rax
0x1800569f3  call    memcpy_s_0
0x1800569f8  mov     rcx, rbx; pv
0x1800569fb  call    cs:__imp_CoTaskMemFree
0x180056a01  inc     r14d
0x180056a04  cmp     r14d, r15d
0x180056a07  jge     short loc_180056A32
0x180056a09  mov     ecx, [rsp+0A8h+var_74]
0x180056a0d  sub     rbp, [rsp+0A8h+var_60]
0x180056a12  add     ecx, dword ptr [rsp+0A8h+var_58]
0x180056a16  mov     [rsp+0A8h+var_74], ecx
0x180056a1a  jmp     short loc_1800569C1
0x180056a1c  xor     r9d, r9d; lpArguments
0x180056a1f  xor     r8d, r8d; nNumberOfArguments
0x180056a22  mov     ecx, 0C000008Ch; dwExceptionCode
0x180056a27  lea     edx, [r9+1]; dwExceptionFlags
0x180056a2b  call    cs:__imp_RaiseException
0x180056a31  int     3; Trap to Debugger
0x180056a32  mov     rax, [rsp+0A8h+arg_8]
0x180056a3a  mov     rcx, [rsp+0A8h+arg_10]
0x180056a42  mov     [rax], r13
0x180056a45  mov     eax, [rsp+0A8h+var_70]
0x180056a49  mov     [rcx], eax
0x180056a4b  test    rsi, rsi
0x180056a4e  jz      short loc_180056A59
0x180056a50  mov     rcx, rsi; Block
0x180056a53  call    cs:__imp_free
0x180056a59  test    rdi, rdi
0x180056a5c  jz      short loc_180056A67
0x180056a5e  mov     rcx, rdi; Block
0x180056a61  call    cs:__imp_free
0x180056a67  xor     eax, eax
0x180056a69  jmp     short loc_180056A70
0x180056a6b  mov     eax, 80004003h
0x180056a70  add     rsp, 68h
0x180056a74  pop     r15
0x180056a76  pop     r14
0x180056a78  pop     r13
0x180056a7a  pop     r12
0x180056a7c  pop     rdi
0x180056a7d  pop     rsi
0x180056a7e  pop     rbp
0x180056a7f  pop     rbx
0x180056a80  retn
```
