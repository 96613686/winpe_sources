# getDXGIMonitorEnum(void)

- ea: `0x180008460`
- end: `0x180008817`
- name: `?getDXGIMonitorEnum@@YAJXZ`
- size: `951`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180002180`

## callees

- `0x180005134`
- `0x180008460`
- `0x18000967e`
- `0x1800096b0`
- `0x180009740`
- `0x18000a010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000853f`
- `ole32!CoTaskMemAlloc` at `0x18000853f`
- `ole32!CoTaskMemFree` at `0x1800087e5`
- `ole32!CoTaskMemFree` at `0x1800087e5`
- `api-ms-win-shcore-scaling-l1-1-1!SetProcessDpiAwareness` at `0x180008502`
- `api-ms-win-shcore-scaling-l1-1-1!SetProcessDpiAwareness` at `0x180008502`
- `dxgi!CreateDXGIFactory1` at `0x180008524`
- `dxgi!CreateDXGIFactory1` at `0x180008524`

## pseudocode

```c
__int64 getDXGIMonitorEnum(void)
{
  struct DXGI_OUTPUT_DESC *v0; // r15
  HRESULT v1; // ebx
  __int64 v2; // rsi
  __int64 *v3; // r12
  int v4; // eax
  __int64 *v5; // r13
  __int64 v6; // rdi
  __int64 *v7; // rdx
  int v8; // eax
  __int64 *v9; // rdx
  int v10; // eax
  __int64 i; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 j; // rsi
  __int64 v15; // rcx
  void *ppFactory; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19[72]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  char v21[72]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-30h] BYREF
  char v23[792]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v24[390]; // [rsp+3F0h] [rbp+2F0h] BYREF
  DXGI_ADAPTER_DESC2 v25[10]; // [rsp+1020h] [rbp+F20h] BYREF

  ppFactory = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v0 = 0;
  memset_0(v24, 0, sizeof(v24));
  v1 = SetProcessDpiAwareness(2);
  if ( v1 >= 0 )
  {
    v1 = CreateDXGIFactory1(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &ppFactory);
    if ( v1 >= 0 )
    {
      v0 = (struct DXGI_OUTPUT_DESC *)CoTaskMemAlloc(0x2580u);
      if ( v0 )
      {
        v2 = 0;
        while ( 1 )
        {
          v3 = (__int64 *)&v19[8 * v2 - 8];
          v4 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)ppFactory + 96LL))(
                 ppFactory,
                 (unsigned int)v2,
                 v3);
          v1 = v4;
          if ( v4 == -2005270526 )
            break;
          if ( v4 < 0 )
            goto LABEL_27;
          v5 = (__int64 *)&v21[8 * v2 - 8];
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))*v3)(
                 *v3,
                 &GUID_0aa1ae0a_fa0e_4b84_8644_e05ff8e5acb5,
                 v5) >= 0 )
          {
            v1 = (*(__int64 (__fastcall **)(__int64, DXGI_ADAPTER_DESC2 *))(*(_QWORD *)*v5 + 88LL))(*v5, &v25[v2]);
            if ( v1 < 0 )
              goto LABEL_27;
            v6 = 0;
            v9 = (__int64 *)&v23[80 * v2 - 8];
            do
            {
              v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*v5 + 56LL))(
                      *v5,
                      (unsigned int)v6,
                      &v9[v6]);
              v1 = v10;
              if ( v10 == -2005270526 )
                break;
              if ( v10 < 0 )
                goto LABEL_27;
              v1 = (*(__int64 (__fastcall **)(_QWORD, struct DXGI_OUTPUT_DESC *))(**(_QWORD **)&v23[80 * v2 - 8 + 8 * v6]
                                                                                + 56LL))(
                     *(_QWORD *)&v23[80 * v2 - 8 + 8 * v6],
                     &v0[(unsigned int)(v6 + 10 * v2)]);
              if ( v1 < 0 )
                goto LABEL_27;
              v6 = (unsigned int)(v6 + 1);
              v9 = (__int64 *)&v23[80 * v2 - 8];
            }
            while ( (unsigned int)v6 < 0xA );
          }
          else
          {
            v1 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*v3 + 80LL))(
                   *v3,
                   &v24[39 * (unsigned int)v2]);
            if ( v1 < 0 )
              goto LABEL_27;
            v6 = 0;
            v7 = (__int64 *)&v23[80 * v2 - 8];
            do
            {
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*v3 + 56LL))(
                     *v3,
                     (unsigned int)v6,
                     &v7[v6]);
              v1 = v8;
              if ( v8 == -2005270526 )
                break;
              if ( v8 < 0 )
                goto LABEL_27;
              v1 = (*(__int64 (__fastcall **)(_QWORD, struct DXGI_OUTPUT_DESC *))(**(_QWORD **)&v23[80 * v2 - 8 + 8 * v6]
                                                                                + 56LL))(
                     *(_QWORD *)&v23[80 * v2 - 8 + 8 * v6],
                     &v0[(unsigned int)(v6 + 10 * v2)]);
              if ( v1 < 0 )
                goto LABEL_27;
              v6 = (unsigned int)(v6 + 1);
              v7 = (__int64 *)&v23[80 * v2 - 8];
            }
            while ( (unsigned int)v6 < 0xA );
          }
          v1 = ParseDXGIData(v2, v6, &v0[(unsigned int)(10 * v2)], v25);
          if ( v1 < 0 )
            goto LABEL_27;
          v2 = (unsigned int)(v2 + 1);
          if ( (unsigned int)v2 >= 0xA )
            goto LABEL_26;
        }
        v1 = 0;
LABEL_26:
        dword_18000F8E4 = v2;
      }
      else
      {
        v1 = -2147024882;
      }
    }
  }
LABEL_27:
  for ( i = 0; i != 10; ++i )
  {
    v12 = *(_QWORD *)&v19[8 * i - 8];
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      *(_QWORD *)&v19[8 * i - 8] = 0;
    }
    v13 = *(_QWORD *)&v21[8 * i - 8];
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      *(_QWORD *)&v21[8 * i - 8] = 0;
    }
    for ( j = 0; j != 10; ++j )
    {
      v15 = *(_QWORD *)&v23[80 * i - 8 + 8 * j];
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        *(_QWORD *)&v23[80 * i - 8 + 8 * j] = 0;
      }
    }
  }
  if ( ppFactory )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  CoTaskMemFree(v0);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180008460  push    rbp
0x180008462  push    rbx
0x180008463  push    rsi
0x180008464  push    rdi
0x180008465  push    r12
0x180008467  push    r13
0x180008469  push    r14
0x18000846b  push    r15
0x18000846d  lea     rbp, [rsp-1BB8h]
0x180008475  mov     eax, 1CB8h
0x18000847a  call    _alloca_probe
0x18000847f  sub     rsp, rax
0x180008482  mov     rax, cs:__security_cookie
0x180008489  xor     rax, rsp
0x18000848c  mov     [rbp+1BF0h+var_50], rax
0x180008493  mov     ebx, 48h ; 'H'
0x180008498  mov     [rsp+1CF0h+ppFactory], 0
0x1800084a1  mov     r8d, ebx; Size
0x1800084a4  mov     [rsp+1CF0h+var_1CC0], 0
0x1800084ad  xor     edx, edx; Val
0x1800084af  lea     rcx, [rsp+1CF0h+var_1CB8]; void *
0x1800084b4  call    memset_0
0x1800084b9  mov     r8d, ebx; Size
0x1800084bc  mov     [rbp+1BF0h+var_1C70], 0
0x1800084c4  xor     edx, edx; Val
0x1800084c6  lea     rcx, [rbp+1BF0h+var_1C68]; void *
0x1800084ca  call    memset_0
0x1800084cf  xor     edx, edx; Val
0x1800084d1  mov     [rbp+1BF0h+var_1C20], 0
0x1800084d9  mov     r8d, 318h; Size
0x1800084df  lea     rcx, [rbp+1BF0h+var_1C18]; void *
0x1800084e3  call    memset_0
0x1800084e8  xor     edx, edx; Val
0x1800084ea  lea     rcx, [rbp+1BF0h+var_1900]; void *
0x1800084f1  mov     r8d, 0C30h; Size
0x1800084f7  xor     r15d, r15d
0x1800084fa  call    memset_0
0x1800084ff  lea     ecx, [rbx-46h]
0x180008502  call    cs:__imp_SetProcessDpiAwareness
0x180008509  nop     dword ptr [rax+rax+00h]
0x18000850e  mov     ebx, eax
0x180008510  test    eax, eax
0x180008512  js      loc_180008743
0x180008518  lea     rdx, [rsp+1CF0h+ppFactory]; ppFactory
0x18000851d  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387; riid
0x180008524  call    cs:__imp_CreateDXGIFactory1
0x18000852b  nop     dword ptr [rax+rax+00h]
0x180008530  mov     ebx, eax
0x180008532  test    eax, eax
0x180008534  js      loc_180008743
0x18000853a  mov     ecx, 2580h; cb
0x18000853f  call    cs:__imp_CoTaskMemAlloc
0x180008546  nop     dword ptr [rax+rax+00h]
0x18000854b  mov     r15, rax
0x18000854e  test    rax, rax
0x180008551  jnz     short loc_18000855D
0x180008553  mov     ebx, 8007000Eh
0x180008558  jmp     loc_180008743
0x18000855d  xor     esi, esi
0x18000855f  mov     rcx, [rsp+1CF0h+ppFactory]
0x180008564  lea     r12, [rsp+1CF0h+var_1CC0]
0x180008569  lea     r12, [r12+rsi*8]
0x18000856d  mov     r14d, esi
0x180008570  mov     r8, r12
0x180008573  mov     edx, esi
0x180008575  mov     rax, [rcx]
0x180008578  mov     rax, [rax+60h]
0x18000857c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008581  mov     ebx, eax
0x180008583  cmp     eax, 887A0002h
0x180008588  jz      loc_18000873B
0x18000858e  test    eax, eax
0x180008590  js      loc_180008743
0x180008596  mov     rcx, [r12]
0x18000859a  lea     r13, [rbp+1BF0h+var_1C70]
0x18000859e  lea     r13, [r13+rsi*8+0]
0x1800085a3  mov     r8, r13
0x1800085a6  lea     rdx, _GUID_0aa1ae0a_fa0e_4b84_8644_e05ff8e5acb5
0x1800085ad  mov     rax, [rcx]
0x1800085b0  mov     rax, [rax]
0x1800085b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b8  test    eax, eax
0x1800085ba  jns     loc_18000866C
0x1800085c0  mov     rcx, [r12]
0x1800085c4  lea     rdx, [rbp+1BF0h+var_1900]
0x1800085cb  imul    rax, r14, 138h
0x1800085d2  mov     r8, [rcx]
0x1800085d5  add     rdx, rax
0x1800085d8  mov     rax, [r8+50h]
0x1800085dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e1  mov     ebx, eax
0x1800085e3  test    eax, eax
0x1800085e5  js      loc_180008743
0x1800085eb  lea     rax, [rsi+rsi*4]
0x1800085ef  xor     edi, edi
0x1800085f1  lea     r14, [rax+rax]
0x1800085f5  lea     rdx, [rbp+1BF0h+var_1C20]
0x1800085f9  lea     rdx, [rdx+r14*8]
0x1800085fd  mov     rcx, [r12]
0x180008601  lea     r8, [rdx+rdi*8]
0x180008605  mov     edx, edi
0x180008607  mov     rax, [rcx]
0x18000860a  mov     rax, [rax+38h]
0x18000860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008613  mov     ebx, eax
0x180008615  cmp     eax, 887A0002h
0x18000861a  jz      loc_180008708
0x180008620  test    eax, eax
0x180008622  js      loc_180008743
0x180008628  lea     rax, [r14+rdi]
0x18000862c  mov     rcx, [rbp+rax*8+1BF0h+var_1C20]
0x180008631  lea     eax, [rsi+rsi*4]
0x180008634  lea     edx, [rdi+rax*2]
0x180008637  lea     rdx, [rdx+rdx*2]
0x18000863b  shl     rdx, 5
0x18000863f  mov     r8, [rcx]
0x180008642  add     rdx, r15
0x180008645  mov     rax, [r8+38h]
0x180008649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864e  mov     ebx, eax
0x180008650  test    eax, eax
0x180008652  js      loc_180008743
0x180008658  inc     edi
0x18000865a  lea     rdx, [rbp+1BF0h+var_1C20]
0x18000865e  lea     rdx, [rdx+r14*8]
0x180008662  cmp     edi, 0Ah
0x180008665  jb      short loc_1800085FD
0x180008667  jmp     loc_180008708
0x18000866c  mov     rcx, [r13+0]
0x180008670  lea     rax, [rsi+rsi*4]
0x180008674  shl     rax, 6
0x180008678  lea     rdx, [rbp+1BF0h+var_CD0]
0x18000867f  add     rdx, rax
0x180008682  mov     r8, [rcx]
0x180008685  mov     rax, [r8+58h]
0x180008689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868e  mov     ebx, eax
0x180008690  test    eax, eax
0x180008692  js      loc_180008743
0x180008698  lea     rax, [rsi+rsi*4]
0x18000869c  xor     edi, edi
0x18000869e  lea     r14, [rax+rax]
0x1800086a2  lea     rdx, [rbp+1BF0h+var_1C20]
0x1800086a6  lea     rdx, [rdx+r14*8]
0x1800086aa  mov     rcx, [r13+0]
0x1800086ae  lea     r8, [rdx+rdi*8]
0x1800086b2  mov     edx, edi
0x1800086b4  mov     rax, [rcx]
0x1800086b7  mov     rax, [rax+38h]
0x1800086bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086c0  mov     ebx, eax
0x1800086c2  cmp     eax, 887A0002h
0x1800086c7  jz      short loc_180008708
0x1800086c9  test    eax, eax
0x1800086cb  js      short loc_180008743
0x1800086cd  lea     rax, [r14+rdi]
0x1800086d1  mov     rcx, [rbp+rax*8+1BF0h+var_1C20]
0x1800086d6  lea     eax, [rsi+rsi*4]
0x1800086d9  lea     edx, [rdi+rax*2]
0x1800086dc  lea     rdx, [rdx+rdx*2]
0x1800086e0  shl     rdx, 5
0x1800086e4  mov     r8, [rcx]
0x1800086e7  add     rdx, r15
0x1800086ea  mov     rax, [r8+38h]
0x1800086ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f3  mov     ebx, eax
0x1800086f5  test    eax, eax
0x1800086f7  js      short loc_180008743
0x1800086f9  inc     edi
0x1800086fb  lea     rdx, [rbp+1BF0h+var_1C20]
0x1800086ff  lea     rdx, [rdx+r14*8]
0x180008703  cmp     edi, 0Ah
0x180008706  jb      short loc_1800086AA
0x180008708  lea     eax, [rsi+rsi*4]
0x18000870b  mov     edx, edi; unsigned int
0x18000870d  add     eax, eax
0x18000870f  lea     r9, [rbp+1BF0h+var_CD0]; struct DXGI_ADAPTER_DESC2 *
0x180008716  mov     ecx, esi; unsigned int
0x180008718  lea     r8, [rax+rax*2]
0x18000871c  shl     r8, 5
0x180008720  add     r8, r15; struct DXGI_OUTPUT_DESC *
0x180008723  call    ?ParseDXGIData@@YAJIIPEAUDXGI_OUTPUT_DESC@@PEBUDXGI_ADAPTER_DESC2@@@Z; ParseDXGIData(uint,uint,DXGI_OUTPUT_DESC *,DXGI_ADAPTER_DESC2 const *)
0x180008728  mov     ebx, eax
0x18000872a  test    eax, eax
0x18000872c  js      short loc_180008743
0x18000872e  inc     esi
0x180008730  cmp     esi, 0Ah
0x180008733  jb      loc_18000855F
0x180008739  jmp     short loc_18000873D
0x18000873b  xor     ebx, ebx
0x18000873d  mov     cs:dword_18000F8E4, esi
0x180008743  xor     edi, edi
0x180008745  mov     rcx, [rsp+rdi*8+1CF0h+var_1CC0]
0x18000874a  test    rcx, rcx
0x18000874d  jz      short loc_180008764
0x18000874f  mov     rax, [rcx]
0x180008752  mov     rax, [rax+10h]
0x180008756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875b  mov     [rsp+rdi*8+1CF0h+var_1CC0], 0
0x180008764  mov     rcx, [rbp+rdi*8+1BF0h+var_1C70]
0x180008769  test    rcx, rcx
0x18000876c  jz      short loc_180008783
0x18000876e  mov     rax, [rcx]
0x180008771  mov     rax, [rax+10h]
0x180008775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877a  mov     [rbp+rdi*8+1BF0h+var_1C70], 0
0x180008783  lea     rax, [rdi+rdi*4]
0x180008787  xor     esi, esi
0x180008789  lea     r14, [rax+rax]
0x18000878d  lea     r12, [rbp+1BF0h+var_1C20]
0x180008791  lea     r12, [r12+r14*8]
0x180008795  mov     rcx, [r12+rsi*8]
0x180008799  test    rcx, rcx
0x18000879c  jz      short loc_1800087B7
0x18000879e  mov     rax, [rcx]
0x1800087a1  mov     rax, [rax+10h]
0x1800087a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087aa  lea     rax, [r14+rsi]
0x1800087ae  mov     [rbp+rax*8+1BF0h+var_1C20], 0
0x1800087b7  inc     rsi
0x1800087ba  cmp     rsi, 0Ah
0x1800087be  jnz     short loc_180008795
0x1800087c0  inc     rdi
0x1800087c3  cmp     rdi, rsi
0x1800087c6  jnz     loc_180008745
0x1800087cc  mov     rcx, [rsp+1CF0h+ppFactory]
0x1800087d1  test    rcx, rcx
0x1800087d4  jz      short loc_1800087E2
0x1800087d6  mov     rax, [rcx]
0x1800087d9  mov     rax, [rax+10h]
0x1800087dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087e2  mov     rcx, r15; pv
0x1800087e5  call    cs:__imp_CoTaskMemFree
0x1800087ec  nop     dword ptr [rax+rax+00h]
0x1800087f1  mov     eax, ebx
0x1800087f3  mov     rcx, [rbp+1BF0h+var_50]
0x1800087fa  xor     rcx, rsp; StackCookie
0x1800087fd  call    __security_check_cookie
0x180008802  add     rsp, 1CB8h
0x180008809  pop     r15
0x18000880b  pop     r14
0x18000880d  pop     r13
0x18000880f  pop     r12
0x180008811  pop     rdi
0x180008812  pop     rsi
0x180008813  pop     rbx
0x180008814  pop     rbp
0x180008815  retn
```
