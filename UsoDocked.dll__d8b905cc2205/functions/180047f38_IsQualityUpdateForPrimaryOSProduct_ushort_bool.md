# IsQualityUpdateForPrimaryOSProduct(ushort *,bool &)

- ea: `0x180047f38`
- end: `0x180048400`
- name: `?IsQualityUpdateForPrimaryOSProduct@@YAJPEAGAEA_N@Z`
- size: `1224`
- prototype: `__int64 __fastcall(unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800478e8`

## callees

- `0x180012090`
- `0x1800183f4`
- `0x180047f38`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048216`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048216`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800481de`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800481de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004822f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004823f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004832e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004833e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004822f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004823f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800482d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004832e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004833e`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x180047f87`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x180047f87`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall IsQualityUpdateForPrimaryOSProduct(unsigned __int16 *a1, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  char v10; // bl
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v22; // [rsp+78h] [rbp+38h] BYREF
  __int64 *v23; // [rsp+80h] [rbp+40h] BYREF
  __int64 *v24; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  if ( (unsigned __int8)IsPE_CreateProductEnumeratorPresent() )
  {
    v17 = 0;
    v4 = PE_CreateProductEnumerator(&v17);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v24 = 0;
      v7 = *v17;
      v24 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v7 + 24))(v17, &v24);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v22 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v24 + 24))(v24, &v22);
        v5 = v9;
        if ( v9 >= 0 )
        {
          if ( v22 )
          {
            v10 = 0;
            v11 = 0;
            do
            {
              v23 = 0;
              v12 = *v24;
              v23 = 0;
              if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 **))(v12 + 32))(v24, v11, &v23) >= 0 )
              {
                v18 = 0;
                v13 = *v23;
                v18 = 0;
                if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v13 + 40))(
                       v23,
                       L"PrimaryOSProduct",
                       &v18) >= 0 )
                {
                  pv = 0;
                  v14 = *v18;
                  pv = 0;
                  if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v14 + 32))(v18, &pv) >= 0 )
                  {
                    if ( (unsigned int)_o__wtoi(pv) == 1 )
                    {
                      v20 = 0;
                      v15 = *v23;
                      v20 = 0;
                      v16 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v15 + 24))(v23, &v20);
                      v5 = v16;
                      if ( v16 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x5B,
                          (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
                          (const char *)(unsigned int)v16,
                          (int)v17);
                        if ( v20 )
                          CoTaskMemFree(v20);
                        if ( pv )
                          CoTaskMemFree(pv);
                        if ( v18 )
                          (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
                        if ( v23 )
                          (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
                        if ( v24 )
                          (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
                        if ( v17 )
                          (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
                        return v5;
                      }
                      if ( !(unsigned int)_o__wcsicmp(v20, a1) )
                      {
                        *a2 = 1;
                        if ( v20 )
                          CoTaskMemFree(v20);
                        if ( pv )
                          CoTaskMemFree(pv);
                        if ( v18 )
                          (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
                        if ( v23 )
                          (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
                        goto LABEL_55;
                      }
                      v10 = 1;
                      if ( v20 )
                        CoTaskMemFree(v20);
                    }
                    if ( pv )
                      CoTaskMemFree(pv);
                    if ( v18 )
                      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
                    if ( v23 )
                      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
                  }
                  else
                  {
                    if ( pv )
                      CoTaskMemFree(pv);
                    if ( v18 )
                      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
                    if ( v23 )
                      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
                  }
                }
                else
                {
                  if ( v18 )
                    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
                  if ( v23 )
                    (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
                }
              }
              else if ( v23 )
              {
                (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
              }
              ++v11;
            }
            while ( v11 < v22 );
            if ( v10 )
            {
LABEL_55:
              if ( v24 )
                (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
              if ( v17 )
                (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x67,
              (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
              (const char *)0x8000FFFFLL,
              (int)v17);
            if ( v24 )
              (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4A,
              (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
              (const char *)0x8000FFFFLL,
              (int)v17);
            if ( v24 )
              (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
          }
          if ( v17 )
            (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
          return 2147549183LL;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
          (const char *)(unsigned int)v9,
          (int)v17);
        if ( v24 )
          (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
        if ( v17 )
          (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
          (const char *)(unsigned int)v8,
          (int)v17);
        if ( v24 )
          (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
        if ( v17 )
          (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
        (const char *)(unsigned int)v4,
        (int)v17);
      if ( v17 )
        (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    }
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40,
    (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
    (const char *)0x8000FFFFLL,
    (int)v17);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180047f38  mov     [rsp-28h+arg_0], rbx
0x180047f3d  push    rbp
0x180047f3e  push    rsi
0x180047f3f  push    rdi
0x180047f40  push    r14
0x180047f42  push    r15
0x180047f44  mov     rbp, rsp
0x180047f47  sub     rsp, 40h
0x180047f4b  mov     rsi, rdx
0x180047f4e  mov     r14, rcx
0x180047f51  xor     r15d, r15d
0x180047f54  mov     [rdx], r15b
0x180047f57  call    IsPE_CreateProductEnumeratorPresent
0x180047f5c  test    al, al
0x180047f5e  jnz     short loc_180047F7F
0x180047f60  mov     rcx, [rbp+28h]; this
0x180047f64  mov     r9d, 8000FFFFh; char *
0x180047f6a  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x180047f71  lea     edx, [r15+40h]; void *
0x180047f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047f7a  jmp     loc_1800483EA
0x180047f7f  mov     [rbp+var_20], r15
0x180047f83  lea     rcx, [rbp+var_20]
0x180047f87  call    cs:__imp_PE_CreateProductEnumerator
0x180047f8d  mov     ebx, eax
0x180047f8f  test    eax, eax
0x180047f91  jns     short loc_180047FC9
0x180047f93  mov     rcx, [rbp+28h]; this
0x180047f97  mov     r9d, eax; char *
0x180047f9a  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x180047fa1  mov     edx, 43h ; 'C'; void *
0x180047fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047fab  nop
0x180047fac  mov     rcx, [rbp+var_20]
0x180047fb0  test    rcx, rcx
0x180047fb3  jz      short loc_180047FC2
0x180047fb5  mov     rax, [rcx]
0x180047fb8  mov     rax, [rax+10h]
0x180047fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fc1  nop
0x180047fc2  mov     eax, ebx
0x180047fc4  jmp     loc_1800483EF
0x180047fc9  mov     [rbp+arg_18], r15
0x180047fcd  mov     rcx, [rbp+var_20]
0x180047fd1  mov     rax, [rcx]
0x180047fd4  mov     [rbp+arg_18], r15
0x180047fd8  lea     rdx, [rbp+arg_18]
0x180047fdc  mov     rax, [rax+18h]
0x180047fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fe5  mov     ebx, eax
0x180047fe7  test    eax, eax
0x180047fe9  jns     short loc_180048032
0x180047feb  mov     rcx, [rbp+28h]; this
0x180047fef  mov     r9d, eax; char *
0x180047ff2  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x180047ff9  mov     edx, 46h ; 'F'; void *
0x180047ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048003  nop
0x180048004  mov     rcx, [rbp+arg_18]
0x180048008  test    rcx, rcx
0x18004800b  jz      short loc_18004801A
0x18004800d  mov     rax, [rcx]
0x180048010  mov     rax, [rax+10h]
0x180048014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048019  nop
0x18004801a  mov     rcx, [rbp+var_20]
0x18004801e  test    rcx, rcx
0x180048021  jz      short loc_180048030
0x180048023  mov     rax, [rcx]
0x180048026  mov     rax, [rax+10h]
0x18004802a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004802f  nop
0x180048030  jmp     short loc_180047FC2
0x180048032  mov     [rbp+arg_8], r15d
0x180048036  mov     rcx, [rbp+arg_18]
0x18004803a  mov     rax, [rcx]
0x18004803d  lea     rdx, [rbp+arg_8]
0x180048041  mov     rax, [rax+18h]
0x180048045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004804a  mov     ebx, eax
0x18004804c  test    eax, eax
0x18004804e  jns     short loc_18004809A
0x180048050  mov     rcx, [rbp+28h]; this
0x180048054  mov     r9d, eax; char *
0x180048057  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x18004805e  mov     edx, 49h ; 'I'; void *
0x180048063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048068  nop
0x180048069  mov     rcx, [rbp+arg_18]
0x18004806d  test    rcx, rcx
0x180048070  jz      short loc_18004807F
0x180048072  mov     rax, [rcx]
0x180048075  mov     rax, [rax+10h]
0x180048079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004807e  nop
0x18004807f  mov     rcx, [rbp+var_20]
0x180048083  test    rcx, rcx
0x180048086  jz      short loc_180048095
0x180048088  mov     rax, [rcx]
0x18004808b  mov     rax, [rax+10h]
0x18004808f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048094  nop
0x180048095  jmp     loc_180047FC2
0x18004809a  mov     eax, [rbp+arg_8]
0x18004809d  test    eax, eax
0x18004809f  jnz     short loc_1800480D6
0x1800480a1  mov     rcx, [rbp+28h]; this
0x1800480a5  mov     r9d, 8000FFFFh; char *
0x1800480ab  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x1800480b2  lea     edx, [rax+4Ah]; void *
0x1800480b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480ba  nop
0x1800480bb  mov     rcx, [rbp+arg_18]
0x1800480bf  test    rcx, rcx
0x1800480c2  jz      short loc_1800480D1
0x1800480c4  mov     rax, [rcx]
0x1800480c7  mov     rax, [rax+10h]
0x1800480cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480d0  nop
0x1800480d1  jmp     loc_1800483D4
0x1800480d6  mov     bl, r15b
0x1800480d9  mov     edi, r15d
0x1800480dc  test    eax, eax
0x1800480de  jz      loc_1800483A2
0x1800480e4  mov     [rbp+arg_10], r15
0x1800480e8  mov     rcx, [rbp+arg_18]
0x1800480ec  mov     rax, [rcx]
0x1800480ef  mov     [rbp+arg_10], r15
0x1800480f3  lea     r8, [rbp+arg_10]
0x1800480f7  mov     edx, edi
0x1800480f9  mov     rax, [rax+20h]
0x1800480fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048102  test    eax, eax
0x180048104  jns     short loc_180048121
0x180048106  mov     rcx, [rbp+arg_10]
0x18004810a  test    rcx, rcx
0x18004810d  jz      short loc_18004811C
0x18004810f  mov     rax, [rcx]
0x180048112  mov     rax, [rax+10h]
0x180048116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004811b  nop
0x18004811c  jmp     loc_180048272
0x180048121  mov     [rbp+var_18], r15
0x180048125  mov     rcx, [rbp+arg_10]
0x180048129  mov     rax, [rcx]
0x18004812c  mov     [rbp+var_18], r15
0x180048130  lea     r8, [rbp+var_18]
0x180048134  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x18004813b  mov     rax, [rax+28h]
0x18004813f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048144  test    eax, eax
0x180048146  jns     short loc_180048179
0x180048148  mov     rcx, [rbp+var_18]
0x18004814c  test    rcx, rcx
0x18004814f  jz      short loc_18004815E
0x180048151  mov     rax, [rcx]
0x180048154  mov     rax, [rax+10h]
0x180048158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004815d  nop
0x18004815e  mov     rcx, [rbp+arg_10]
0x180048162  test    rcx, rcx
0x180048165  jz      short loc_180048174
0x180048167  mov     rax, [rcx]
0x18004816a  mov     rax, [rax+10h]
0x18004816e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048173  nop
0x180048174  jmp     loc_180048272
0x180048179  mov     [rbp+pv], r15
0x18004817d  mov     rcx, [rbp+var_18]
0x180048181  mov     rax, [rcx]
0x180048184  mov     [rbp+pv], r15
0x180048188  lea     rdx, [rbp+pv]
0x18004818c  mov     rax, [rax+20h]
0x180048190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048195  test    eax, eax
0x180048197  jns     short loc_1800481DA
0x180048199  mov     rcx, [rbp+pv]; pv
0x18004819d  test    rcx, rcx
0x1800481a0  jz      short loc_1800481A9
0x1800481a2  call    cs:__imp_CoTaskMemFree
0x1800481a8  nop
0x1800481a9  mov     rcx, [rbp+var_18]
0x1800481ad  test    rcx, rcx
0x1800481b0  jz      short loc_1800481BF
0x1800481b2  mov     rax, [rcx]
0x1800481b5  mov     rax, [rax+10h]
0x1800481b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481be  nop
0x1800481bf  mov     rcx, [rbp+arg_10]
0x1800481c3  test    rcx, rcx
0x1800481c6  jz      short loc_1800481D5
0x1800481c8  mov     rax, [rcx]
0x1800481cb  mov     rax, [rax+10h]
0x1800481cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481d4  nop
0x1800481d5  jmp     loc_180048272
0x1800481da  mov     rcx, [rbp+pv]
0x1800481de  call    cs:__imp__o__wtoi
0x1800481e4  cmp     eax, 1
0x1800481e7  jnz     short loc_180048236
0x1800481e9  mov     [rbp+var_8], r15
0x1800481ed  mov     rcx, [rbp+arg_10]
0x1800481f1  mov     rax, [rcx]
0x1800481f4  mov     [rbp+var_8], r15
0x1800481f8  lea     rdx, [rbp+var_8]
0x1800481fc  mov     rax, [rax+18h]
0x180048200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048205  mov     ebx, eax
0x180048207  test    eax, eax
0x180048209  js      loc_18004830C
0x18004820f  mov     rdx, r14
0x180048212  mov     rcx, [rbp+var_8]
0x180048216  call    cs:__imp__o__wcsicmp
0x18004821c  test    eax, eax
0x18004821e  jz      loc_1800482B8
0x180048224  mov     bl, 1
0x180048226  mov     rcx, [rbp+var_8]; pv
0x18004822a  test    rcx, rcx
0x18004822d  jz      short loc_180048236
0x18004822f  call    cs:__imp_CoTaskMemFree
0x180048235  nop
0x180048236  mov     rcx, [rbp+pv]; pv
0x18004823a  test    rcx, rcx
0x18004823d  jz      short loc_180048246
0x18004823f  call    cs:__imp_CoTaskMemFree
0x180048245  nop
0x180048246  mov     rcx, [rbp+var_18]
0x18004824a  test    rcx, rcx
0x18004824d  jz      short loc_18004825C
0x18004824f  mov     rax, [rcx]
0x180048252  mov     rax, [rax+10h]
0x180048256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004825b  nop
0x18004825c  mov     rcx, [rbp+arg_10]
0x180048260  test    rcx, rcx
0x180048263  jz      short loc_180048272
0x180048265  mov     rax, [rcx]
0x180048268  mov     rax, [rax+10h]
0x18004826c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048271  nop
0x180048272  inc     edi
0x180048274  cmp     edi, [rbp+arg_8]
0x180048277  jb      loc_1800480E4
0x18004827d  test    bl, bl
0x18004827f  jz      loc_1800483A2
0x180048285  mov     rcx, [rbp+arg_18]
0x180048289  test    rcx, rcx
0x18004828c  jz      short loc_18004829B
0x18004828e  mov     rax, [rcx]
0x180048291  mov     rax, [rax+10h]
0x180048295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004829a  nop
0x18004829b  mov     rcx, [rbp+var_20]
0x18004829f  test    rcx, rcx
0x1800482a2  jz      short loc_1800482B1
0x1800482a4  mov     rax, [rcx]
0x1800482a7  mov     rax, [rax+10h]
0x1800482ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482b0  nop
0x1800482b1  xor     eax, eax
0x1800482b3  jmp     loc_1800483EF
0x1800482b8  mov     byte ptr [rsi], 1
0x1800482bb  mov     rcx, [rbp+var_8]; pv
0x1800482bf  test    rcx, rcx
0x1800482c2  jz      short loc_1800482CB
0x1800482c4  call    cs:__imp_CoTaskMemFree
0x1800482ca  nop
0x1800482cb  mov     rcx, [rbp+pv]; pv
0x1800482cf  test    rcx, rcx
0x1800482d2  jz      short loc_1800482DB
0x1800482d4  call    cs:__imp_CoTaskMemFree
0x1800482da  nop
0x1800482db  mov     rcx, [rbp+var_18]
0x1800482df  test    rcx, rcx
0x1800482e2  jz      short loc_1800482F1
0x1800482e4  mov     rax, [rcx]
0x1800482e7  mov     rax, [rax+10h]
0x1800482eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f0  nop
0x1800482f1  mov     rcx, [rbp+arg_10]
0x1800482f5  test    rcx, rcx
0x1800482f8  jz      short loc_180048307
0x1800482fa  mov     rax, [rcx]
0x1800482fd  mov     rax, [rax+10h]
0x180048301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048306  nop
0x180048307  jmp     loc_180048285
0x18004830c  mov     rcx, [rbp+28h]; this
0x180048310  mov     r9d, ebx; char *
0x180048313  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x18004831a  mov     edx, 5Bh ; '['; void *
0x18004831f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048324  nop
0x180048325  mov     rcx, [rbp+var_8]; pv
0x180048329  test    rcx, rcx
0x18004832c  jz      short loc_180048335
0x18004832e  call    cs:__imp_CoTaskMemFree
0x180048334  nop
0x180048335  mov     rcx, [rbp+pv]; pv
0x180048339  test    rcx, rcx
  ... truncated ...
```
