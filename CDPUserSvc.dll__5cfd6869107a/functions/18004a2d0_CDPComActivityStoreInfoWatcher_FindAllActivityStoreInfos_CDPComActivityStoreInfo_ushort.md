# CDPComActivityStoreInfoWatcher::FindAllActivityStoreInfos(CDPComActivityStoreInfo * *,ushort *)

- ea: `0x18004a2d0`
- end: `0x18004a4af`
- name: `?FindAllActivityStoreInfos@CDPComActivityStoreInfoWatcher@@UEAAJPEAPEAUCDPComActivityStoreInfo@@PEAG@Z`
- size: `479`
- prototype: `__int64 __fastcall(CDPComActivityStoreInfoWatcher *__hidden this, struct CDPComActivityStoreInfo **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003678`
- `0x180011328`
- `0x18002d1c8`
- `0x18004a204`
- `0x18004a2d0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a494`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a494`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a3aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a3aa`

## pseudocode

```c
__int64 __fastcall CDPComActivityStoreInfoWatcher::FindAllActivityStoreInfos(
        CDPComActivityStoreInfoWatcher *this,
        struct CDPComActivityStoreInfo **a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  unsigned int v13; // edi
  char *v14; // rax
  char *v15; // rbx
  unsigned __int16 v16; // r14
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rdi
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r9
  int v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 v26; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+58h] BYREF

  if ( !a2 )
  {
    v27 = -2147024809;
    v23 = 58;
    Log<long &,char const (&)[38],int>((__int64)this, 0, &v27, a4, &v23);
    return v27;
  }
  *a3 = 0;
  *a2 = 0;
  v25[0] = 0;
  v7 = *((_QWORD *)this + 17);
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  v9 = v8(v7, v25);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)v25[0] + 32LL))(v25[0], &v26);
    if ( v9 >= 0 )
    {
      if ( v26 )
      {
        v14 = (char *)CoTaskMemAlloc(16LL * v26);
        v15 = v14;
        if ( !v14 )
        {
          v27 = -2147024882;
          v23 = 73;
          goto LABEL_8;
        }
        memset_0(v14, 0, 16LL * v26);
        v16 = 0;
        if ( v26 )
        {
          while ( 1 )
          {
            v24 = 0;
            v17 = v25[0];
            v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25[0] + 24LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            v19 = v18(v17, v16, &v24);
            if ( v19 < 0 )
              break;
            if ( (int)CDPActivityStoreInfoToComActivityStoreInfo(v24, &v15[16 * v16]) < 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
              goto LABEL_15;
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            if ( ++v16 >= v26 )
              goto LABEL_15;
          }
          v27 = v19;
          v23 = 80;
          Log<long &,char const (&)[38],int>(v21, v20, &v27, v22, &v23);
          v13 = v27;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
          CoTaskMemFree(v15);
          goto LABEL_17;
        }
LABEL_15:
        *a2 = (struct CDPComActivityStoreInfo *)v15;
        *a3 = v16;
      }
      v13 = 0;
      goto LABEL_17;
    }
    v23 = 66;
  }
  else
  {
    v23 = 64;
  }
  v27 = v9;
LABEL_8:
  Log<long &,char const (&)[38],int>(v11, v10, &v27, v12, &v23);
  v13 = v27;
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
  return v13;
}

```

## disassembly

```asm
0x18004a2d0  mov     [rsp-38h+arg_0], rbx
0x18004a2d5  push    rbp
0x18004a2d6  push    rsi
0x18004a2d7  push    rdi
0x18004a2d8  push    r12
0x18004a2da  push    r13
0x18004a2dc  push    r14
0x18004a2de  push    r15
0x18004a2e0  mov     rbp, rsp
0x18004a2e3  sub     rsp, 50h
0x18004a2e7  mov     r12, r8
0x18004a2ea  mov     r15, rdx
0x18004a2ed  xor     r13d, r13d
0x18004a2f0  test    rdx, rdx
0x18004a2f3  jnz     short loc_18004A31D
0x18004a2f5  mov     [rbp+arg_18], 80070057h
0x18004a2fc  mov     [rbp+var_20], 3Ah ; ':'
0x18004a303  lea     rax, [rbp+var_20]
0x18004a307  mov     [rsp+50h+var_30], rax
0x18004a30c  lea     r8, [rbp+arg_18]
0x18004a310  call    ??$Log@AEAJAEAY0CG@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CG@$$CBD$$QEAH@Z; Log<long &,char const (&)[38],int>(CDPLogLevel,char const *,long &,char const (&)[38],int &&)
0x18004a315  mov     eax, [rbp+arg_18]
0x18004a318  jmp     loc_18004A44A
0x18004a31d  mov     [r8], r13w
0x18004a321  mov     [rdx], r13
0x18004a324  mov     [rbp+var_10], r13
0x18004a328  mov     rdi, [rcx+88h]
0x18004a32f  mov     rax, [rdi]
0x18004a332  mov     rbx, [rax+18h]
0x18004a336  lea     rcx, [rbp+var_10]
0x18004a33a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a33f  lea     rdx, [rbp+var_10]
0x18004a343  mov     rcx, rdi
0x18004a346  mov     rax, rbx
0x18004a349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a34e  test    eax, eax
0x18004a350  jns     short loc_18004A35B
0x18004a352  mov     [rbp+var_20], 40h ; '@'
0x18004a359  jmp     short loc_18004A37A
0x18004a35b  mov     rcx, [rbp+var_10]
0x18004a35f  mov     rax, [rcx]
0x18004a362  lea     rdx, [rbp+arg_8]
0x18004a366  mov     rax, [rax+20h]
0x18004a36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a36f  test    eax, eax
0x18004a371  jns     short loc_18004A397
0x18004a373  mov     [rbp+var_20], 42h ; 'B'
0x18004a37a  mov     [rbp+arg_18], eax
0x18004a37d  lea     rax, [rbp+var_20]
0x18004a381  mov     [rsp+50h+var_30], rax
0x18004a386  lea     r8, [rbp+arg_18]
0x18004a38a  call    ??$Log@AEAJAEAY0CG@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CG@$$CBD$$QEAH@Z; Log<long &,char const (&)[38],int>(CDPLogLevel,char const *,long &,char const (&)[38],int &&)
0x18004a38f  mov     edi, [rbp+arg_18]
0x18004a392  jmp     loc_18004A43F
0x18004a397  movzx   eax, [rbp+arg_8]
0x18004a39b  test    ax, ax
0x18004a39e  jz      loc_18004A43C
0x18004a3a4  mov     ecx, eax
0x18004a3a6  shl     rcx, 4; cb
0x18004a3aa  call    cs:__imp_CoTaskMemAlloc
0x18004a3b0  mov     rbx, rax
0x18004a3b3  test    rax, rax
0x18004a3b6  jz      loc_18004A49C
0x18004a3bc  movzx   r8d, [rbp+arg_8]
0x18004a3c1  shl     r8, 4; Size
0x18004a3c5  xor     edx, edx; Val
0x18004a3c7  mov     rcx, rax; void *
0x18004a3ca  call    memset_0
0x18004a3cf  mov     r14d, r13d
0x18004a3d2  cmp     r13w, [rbp+arg_8]
0x18004a3d7  jnb     short loc_18004A434
0x18004a3d9  mov     [rbp+var_18], r13
0x18004a3dd  mov     rsi, [rbp+var_10]
0x18004a3e1  mov     rax, [rsi]
0x18004a3e4  mov     rdi, [rax+18h]
0x18004a3e8  lea     rcx, [rbp+var_18]
0x18004a3ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a3f1  lea     r8, [rbp+var_18]
0x18004a3f5  movzx   edx, r14w
0x18004a3f9  mov     rcx, rsi
0x18004a3fc  mov     rax, rdi
0x18004a3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a404  test    eax, eax
0x18004a406  js      short loc_18004A469
0x18004a408  movzx   edx, r14w
0x18004a40c  shl     rdx, 4
0x18004a410  add     rdx, rbx
0x18004a413  mov     rcx, [rbp+var_18]
0x18004a417  call    CDPActivityStoreInfoToComActivityStoreInfo
0x18004a41c  lea     rcx, [rbp+var_18]
0x18004a420  test    eax, eax
0x18004a422  js      short loc_18004A462
0x18004a424  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a429  inc     r14w
0x18004a42d  cmp     r14w, [rbp+arg_8]
0x18004a432  jb      short loc_18004A3D9
0x18004a434  mov     [r15], rbx
0x18004a437  mov     [r12], r14w
0x18004a43c  mov     edi, r13d
0x18004a43f  lea     rcx, [rbp+var_10]
0x18004a443  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a448  mov     eax, edi
0x18004a44a  mov     rbx, [rsp+50h+arg_0]
0x18004a452  add     rsp, 50h
0x18004a456  pop     r15
0x18004a458  pop     r14
0x18004a45a  pop     r13
0x18004a45c  pop     r12
0x18004a45e  pop     rdi
0x18004a45f  pop     rsi
0x18004a460  pop     rbp
0x18004a461  retn
0x18004a462  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a467  jmp     short loc_18004A434
0x18004a469  mov     [rbp+arg_18], eax
0x18004a46c  mov     [rbp+var_20], 50h ; 'P'
0x18004a473  lea     rax, [rbp+var_20]
0x18004a477  mov     [rsp+50h+var_30], rax
0x18004a47c  lea     r8, [rbp+arg_18]
0x18004a480  call    ??$Log@AEAJAEAY0CG@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CG@$$CBD$$QEAH@Z; Log<long &,char const (&)[38],int>(CDPLogLevel,char const *,long &,char const (&)[38],int &&)
0x18004a485  mov     edi, [rbp+arg_18]
0x18004a488  lea     rcx, [rbp+var_18]
0x18004a48c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a491  mov     rcx, rbx; pv
0x18004a494  call    cs:__imp_CoTaskMemFree
0x18004a49a  jmp     short loc_18004A43F
0x18004a49c  mov     [rbp+arg_18], 8007000Eh
0x18004a4a3  mov     [rbp+var_20], 49h ; 'I'
0x18004a4aa  jmp     loc_18004A37D
```
