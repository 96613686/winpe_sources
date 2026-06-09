# CCompositeSystemEffect::GetEffectsList(_GUID * *,uint *,void *)

- ea: `0x180056330`
- end: `0x1800565f1`
- name: `?GetEffectsList@CCompositeSystemEffect@@UEAAJPEAPEAU_GUID@@PEAIPEAX@Z`
- size: `705`
- prototype: `__int64 __fastcall(CCompositeSystemEffect *__hidden this, struct _GUID **, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001280c`
- `0x180056330`
- `0x1800565f8`
- `0x18006e130`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180056408`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18005645e`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180056408`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18005645e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800564c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800564d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056505`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056513`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800565c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800565d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800564c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800564d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056505`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056513`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800565c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800565d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005659b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005659b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800564ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800564ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005656b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005656b`

## string_xrefs

- `0x1800564a9`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`

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
0x180056330  mov     rax, rsp
0x180056333  mov     [rax+20h], r9
0x180056337  mov     [rax+18h], r8
0x18005633b  mov     [rax+10h], rdx
0x18005633f  mov     [rax+8], rcx
0x180056343  push    rbx
0x180056344  push    rbp
0x180056345  push    rsi
0x180056346  push    rdi
0x180056347  push    r12
0x180056349  push    r13
0x18005634b  push    r14
0x18005634d  push    r15
0x18005634f  sub     rsp, 68h
0x180056353  mov     rax, r8
0x180056356  mov     r8, rcx
0x180056359  mov     rbx, r9
0x18005635c  test    rdx, rdx
0x18005635f  jz      loc_1800565DB
0x180056365  test    rax, rax
0x180056368  jz      loc_1800565DB
0x18005636e  xor     ecx, ecx
0x180056370  xor     edi, edi
0x180056372  xor     r15d, r15d
0x180056375  mov     [rdx], rcx
0x180056378  xor     r13d, r13d
0x18005637b  mov     [rax], ecx
0x18005637d  xor     esi, esi
0x18005637f  mov     [rsp+0A8h+var_74], ecx
0x180056383  xor     r12d, r12d
0x180056386  xor     ebp, ebp
0x180056388  xor     r14d, r14d
0x18005638b  mov     [rsp+0A8h+var_70], ebp
0x18005638f  cmp     r14d, [r8+78h]
0x180056393  jge     loc_1800564E0
0x180056399  lea     rcx, [r8+70h]
0x18005639d  mov     [rsp+0A8h+var_68], 0
0x1800563a6  mov     edx, r14d
0x1800563a9  mov     [rsp+0A8h+var_78], 0
0x1800563b1  call    ??A?$CSimpleArray@PEAUHINSTANCE__@@V?$CSimpleArrayEqualHelper@PEAUHINSTANCE__@@@ATL@@@ATL@@QEAAAEAPEAUHINSTANCE__@@H@Z; ATL::CSimpleArray<HINSTANCE__ *,ATL::CSimpleArrayEqualHelper<HINSTANCE__ *>>::operator[](int)
0x1800563b6  mov     r9, rbx
0x1800563b9  lea     r8, [rsp+0A8h+var_78]
0x1800563be  lea     rdx, [rsp+0A8h+var_68]
0x1800563c3  mov     rcx, [rax]
0x1800563c6  mov     rax, [rcx]
0x1800563c9  mov     rax, [rax+18h]
0x1800563cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563d2  mov     ebx, eax
0x1800563d4  test    eax, eax
0x1800563d6  js      loc_1800564A1
0x1800563dc  cmp     r15d, r13d
0x1800563df  jnz     short loc_180056419
0x1800563e1  test    r13d, r13d
0x1800563e4  jnz     short loc_1800563EC
0x1800563e6  lea     ebx, [r13+1]
0x1800563ea  jmp     short loc_1800563F4
0x1800563ec  lea     ebx, [r15+r15]
0x1800563f0  test    ebx, ebx
0x1800563f2  js      short loc_180056430
0x1800563f4  mov     edx, ebx
0x1800563f6  cmp     rdx, 0FFFFFFFh
0x1800563fd  ja      short loc_180056430
0x1800563ff  mov     r8d, 8
0x180056405  mov     rcx, rdi
0x180056408  call    cs:__imp__o__recalloc
0x18005640e  test    rax, rax
0x180056411  jz      short loc_180056430
0x180056413  mov     r13d, ebx
0x180056416  mov     rdi, rax
0x180056419  movsxd  rax, r15d
0x18005641c  lea     rcx, [rdi+rax*8]
0x180056420  test    rcx, rcx
0x180056423  jz      short loc_18005642D
0x180056425  mov     rax, [rsp+0A8h+var_68]
0x18005642a  mov     [rcx], rax
0x18005642d  inc     r15d
0x180056430  mov     ecx, [rsp+0A8h+var_74]
0x180056434  cmp     r12d, ecx
0x180056437  jnz     short loc_180056470
0x180056439  test    ecx, ecx
0x18005643b  jnz     short loc_180056442
0x18005643d  lea     ebx, [rcx+1]
0x180056440  jmp     short loc_18005644A
0x180056442  lea     ebx, [r12+r12]
0x180056446  test    ebx, ebx
0x180056448  js      short loc_180056485
0x18005644a  mov     edx, ebx
0x18005644c  cmp     rdx, 1FFFFFFFh
0x180056453  ja      short loc_180056485
0x180056455  mov     r8d, 4
0x18005645b  mov     rcx, rsi
0x18005645e  call    cs:__imp__o__recalloc
0x180056464  test    rax, rax
0x180056467  jz      short loc_180056485
0x180056469  mov     [rsp+0A8h+var_74], ebx
0x18005646d  mov     rsi, rax
0x180056470  movsxd  rax, r12d
0x180056473  lea     rcx, [rsi+rax*4]
0x180056477  test    rcx, rcx
0x18005647a  jz      short loc_180056482
0x18005647c  mov     eax, [rsp+0A8h+var_78]
0x180056480  mov     [rcx], eax
0x180056482  inc     r12d
0x180056485  add     ebp, [rsp+0A8h+var_78]
0x180056489  mov     r8, [rsp+0A8h+arg_0]
0x180056491  inc     r14d
0x180056494  mov     rbx, [rsp+0A8h+arg_18]
0x18005649c  jmp     loc_18005638B
0x1800564a1  mov     rcx, [rsp+0A8h]; this
0x1800564a9  lea     r8, aAvcoreAudiocor_31; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800564b0  mov     r9d, ebx; char *
0x1800564b3  mov     edx, 4CBh; void *
0x1800564b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800564bd  test    rsi, rsi
0x1800564c0  jz      short loc_1800564CB
0x1800564c2  mov     rcx, rsi; Block
0x1800564c5  call    cs:__imp_free
0x1800564cb  test    rdi, rdi
0x1800564ce  jz      short loc_1800564D9
0x1800564d0  mov     rcx, rdi; Block
0x1800564d3  call    cs:__imp_free
0x1800564d9  mov     eax, ebx
0x1800564db  jmp     loc_1800565E0
0x1800564e0  test    ebp, ebp
0x1800564e2  jz      loc_1800565BB
0x1800564e8  shl     rbp, 4
0x1800564ec  mov     rcx, rbp; cb
0x1800564ef  call    cs:__imp_CoTaskMemAlloc
0x1800564f5  mov     r13, rax
0x1800564f8  test    rax, rax
0x1800564fb  jnz     short loc_180056523
0x1800564fd  test    rsi, rsi
0x180056500  jz      short loc_18005650B
0x180056502  mov     rcx, rsi; Block
0x180056505  call    cs:__imp_free
0x18005650b  test    rdi, rdi
0x18005650e  jz      short loc_180056519
0x180056510  mov     rcx, rdi; Block
0x180056513  call    cs:__imp_free
0x180056519  mov     eax, 8007000Eh
0x18005651e  jmp     loc_1800565E0
0x180056523  xor     ecx, ecx
0x180056525  xor     r14d, r14d
0x180056528  mov     [rsp+0A8h+var_74], ecx
0x18005652c  test    r15d, r15d
0x18005652f  jle     short loc_1800565A2
0x180056531  test    r14d, r14d
0x180056534  js      short loc_18005658C
0x180056536  cmp     r14d, r12d
0x180056539  jge     short loc_18005658C
0x18005653b  movsxd  rax, r14d
0x18005653e  mov     rdx, rbp; DestinationSize
0x180056541  shl     rcx, 4
0x180056545  add     rcx, r13; Destination
0x180056548  mov     rbx, [rdi+rax*8]
0x18005654c  mov     eax, [rsi+rax*4]
0x18005654f  mov     r8, rbx; Source
0x180056552  mov     [rsp+0A8h+var_58], rax
0x180056557  shl     rax, 4
0x18005655b  mov     r9, rax; SourceSize
0x18005655e  mov     [rsp+0A8h+var_60], rax
0x180056563  call    memcpy_s_0
0x180056568  mov     rcx, rbx; pv
0x18005656b  call    cs:__imp_CoTaskMemFree
0x180056571  inc     r14d
0x180056574  cmp     r14d, r15d
0x180056577  jge     short loc_1800565A2
0x180056579  mov     ecx, [rsp+0A8h+var_74]
0x18005657d  sub     rbp, [rsp+0A8h+var_60]
0x180056582  add     ecx, dword ptr [rsp+0A8h+var_58]
0x180056586  mov     [rsp+0A8h+var_74], ecx
0x18005658a  jmp     short loc_180056531
0x18005658c  xor     r9d, r9d; lpArguments
0x18005658f  xor     r8d, r8d; nNumberOfArguments
0x180056592  mov     ecx, 0C000008Ch; dwExceptionCode
0x180056597  lea     edx, [r9+1]; dwExceptionFlags
0x18005659b  call    cs:__imp_RaiseException
0x1800565a1  int     3; Trap to Debugger
0x1800565a2  mov     rax, [rsp+0A8h+arg_8]
0x1800565aa  mov     rcx, [rsp+0A8h+arg_10]
0x1800565b2  mov     [rax], r13
0x1800565b5  mov     eax, [rsp+0A8h+var_70]
0x1800565b9  mov     [rcx], eax
0x1800565bb  test    rsi, rsi
0x1800565be  jz      short loc_1800565C9
0x1800565c0  mov     rcx, rsi; Block
0x1800565c3  call    cs:__imp_free
0x1800565c9  test    rdi, rdi
0x1800565cc  jz      short loc_1800565D7
0x1800565ce  mov     rcx, rdi; Block
0x1800565d1  call    cs:__imp_free
0x1800565d7  xor     eax, eax
0x1800565d9  jmp     short loc_1800565E0
0x1800565db  mov     eax, 80004003h
0x1800565e0  add     rsp, 68h
0x1800565e4  pop     r15
0x1800565e6  pop     r14
0x1800565e8  pop     r13
0x1800565ea  pop     r12
0x1800565ec  pop     rdi
0x1800565ed  pop     rsi
0x1800565ee  pop     rbp
0x1800565ef  pop     rbx
0x1800565f0  retn
```
