# ExecuteSendWwanNotification(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000fc50`
- end: `0x14000fff1`
- name: `?ExecuteSendWwanNotification@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `929`
- prototype: `__int64 __fastcall(int, _DWORD **, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x140002168`
- `0x14000e868`
- `0x14000e908`
- `0x14000fc50`
- `0x140010178`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000fdbc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000fdbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000feeb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000feeb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000fcb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000fcb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ff25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ff25`

## pseudocode

```c
__int64 __fastcall ExecuteSendWwanNotification(int a1, char **a2, __int64 a3)
{
  char *v4; // r15
  __int64 v5; // rbx
  HRESULT v6; // esi
  int v7; // r8d
  char *v8; // rdx
  __int64 v9; // r12
  unsigned __int64 v10; // rcx
  _DWORD *v11; // rax
  unsigned __int64 v12; // rsi
  char *v13; // rsi
  HANDLE EventW; // r14
  __int64 *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64; // rax
  HANDLE v19; // [rsp+90h] [rbp-88h] BYREF
  __int64 v20; // [rsp+98h] [rbp-80h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-68h]
  char *v24; // [rsp+C0h] [rbp-58h] BYREF
  int v25; // [rsp+C8h] [rbp-50h]
  _BYTE v26[12]; // [rsp+D0h] [rbp-48h]
  int v27; // [rsp+120h] [rbp+8h] BYREF
  int v28; // [rsp+128h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+138h] [rbp+20h] BYREF

  v27 = a1;
  v4 = *a2;
  v24 = *a2;
  ppv = 0;
  v21 = 0;
  v20 = 0;
  v5 = 0;
  v23 = 0;
  *(_QWORD *)&v26[4] = 0;
  v28 = 0;
  v19 = 0;
  v6 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  if ( v6 < 0 )
    goto LABEL_24;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, &v20);
  if ( v6 < 0 )
    goto LABEL_24;
  v6 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)v20 + 40LL))(
         v20,
         v4 + 278,
         0x200000,
         1);
  if ( v6 < 0 )
    goto LABEL_24;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v21);
  if ( v6 < 0 )
    goto LABEL_24;
  *(_DWORD *)v26 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    LOBYTE(v27) = 0;
    v8 = *(char **)a3;
    v9 = *(_QWORD *)(a3 + 8);
    v10 = v9 - *(_QWORD *)a3;
    if ( v10 <= 8 )
    {
      if ( v10 >= 8 )
        goto LABEL_43;
      if ( *(_QWORD *)(a3 + 16) - (_QWORD)v8 < 8u )
      {
        std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a3, v8, &v27);
        goto LABEL_43;
      }
      v12 = 8 - v10;
      memset_0(*(void **)(a3 + 8), 0, 8 - v10);
      v11 = (_DWORD *)(v12 + v9);
    }
    else
    {
      v11 = v8 + 8;
    }
    *(_QWORD *)(a3 + 8) = v11;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v27 = -2147024888;
      v6 = -2147024888;
      v5 = v23;
      EventW = v19;
      LODWORD(v4) = (_DWORD)v24;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000FEFC);
LABEL_22:
      if ( EventW )
        CloseHandle(EventW);
LABEL_24:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v7, (_DWORD)v4 + 4, v6);
      }
      if ( v6 < 0 )
      {
        if ( (v6 & 0x1FFF0000) == 0x70000 )
          v6 = (unsigned __int16)v6;
      }
      else
      {
        v6 = 0;
      }
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
       = (unsigned int)v6;
    }
  }
LABEL_43:
  v13 = *(char **)a3;
  v24 = *(char **)a3;
  EventW = CreateEventW(0, 1, 0, 0);
  v19 = EventW;
  if ( EventW )
  {
    *(_DWORD *)v13 = *(_DWORD *)v4;
    v15 = Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(
            &v22,
            (__int64 *)&v19,
            (__int64 *)&v24);
    v16 = *v15;
    *v15 = 0;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      v5 = v16;
      v23 = v16;
    }
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v24 = *(char **)v26;
    v25 = *(_DWORD *)&v26[8];
    v6 = (*(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, int, char *, _DWORD *, _QWORD, char **, _DWORD, _DWORD, _QWORD, __int64, _QWORD, _DWORD, int *))(*(_QWORD *)v21 + 64LL))(
           v21,
           v4 + 22,
           v4 + 278,
           0,
           1,
           v4 + 534,
           (_DWORD *)v4 + 1,
           0,
           &v24,
           0,
           0,
           0,
           v5,
           0,
           0,
           &v28);
    if ( v6 >= 0 && WaitForSingleObject(EventW, 0x7530u) )
      v6 = -2147023436;
  }
  else
  {
    v6 = -2147024888;
  }
  goto LABEL_22;
}

```

## disassembly

```asm
0x14000fc50  mov     rax, rsp
0x14000fc53  mov     [rax+8], ecx
0x14000fc56  push    rbx
0x14000fc57  push    rsi
0x14000fc58  push    rdi
0x14000fc59  push    r12
0x14000fc5b  push    r13
0x14000fc5d  push    r14
0x14000fc5f  push    r15
0x14000fc61  sub     rsp, 0E0h
0x14000fc68  mov     r14, r8
0x14000fc6b  mov     r15, [rdx]
0x14000fc6e  mov     [rsp+118h+var_58], r15
0x14000fc76  xor     edi, edi
0x14000fc78  mov     [rax+20h], rdi
0x14000fc7c  mov     [rax-78h], rdi
0x14000fc80  mov     [rax-80h], rdi
0x14000fc84  mov     ebx, edi
0x14000fc86  mov     [rax-68h], rbx
0x14000fc8a  mov     [rax-44h], rdi
0x14000fc8e  mov     [rax+10h], edi
0x14000fc91  mov     [rax-88h], rdi
0x14000fc98  lea     rax, [rax+20h]
0x14000fc9c  mov     [rsp+118h+ppv], rax; ppv
0x14000fca1  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14000fca8  xor     edx, edx; pUnkOuter
0x14000fcaa  lea     r8d, [rdi+4]; dwClsContext
0x14000fcae  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14000fcb5  call    cs:__imp_CoCreateInstance
0x14000fcbb  mov     esi, eax
0x14000fcbd  test    eax, eax
0x14000fcbf  js      loc_14000FF2B
0x14000fcc5  mov     rcx, [rsp+118h+arg_18]
0x14000fccd  mov     rax, [rcx]
0x14000fcd0  lea     rdx, [rsp+118h+var_80]
0x14000fcd8  mov     rax, [rax+30h]
0x14000fcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fce1  mov     esi, eax
0x14000fce3  test    eax, eax
0x14000fce5  js      loc_14000FF2B
0x14000fceb  mov     rcx, [rsp+118h+var_80]
0x14000fcf3  lea     r13, [r15+116h]
0x14000fcfa  mov     rax, [rcx]
0x14000fcfd  lea     r9d, [rdi+1]
0x14000fd01  mov     r8d, 200000h
0x14000fd07  mov     rdx, r13
0x14000fd0a  mov     rax, [rax+28h]
0x14000fd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd13  mov     esi, eax
0x14000fd15  test    eax, eax
0x14000fd17  js      loc_14000FF2B
0x14000fd1d  mov     rcx, [rsp+118h+arg_18]
0x14000fd25  mov     rax, [rcx]
0x14000fd28  lea     rdx, [rsp+118h+var_78]
0x14000fd30  mov     rax, [rax+18h]
0x14000fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd39  mov     esi, eax
0x14000fd3b  test    eax, eax
0x14000fd3d  js      loc_14000FF2B
0x14000fd43  mov     dword ptr [rsp+118h+var_48], edi
0x14000fd4a  mov     byte ptr [rsp+118h+arg_0], dil
0x14000fd52  mov     rdx, [r14]
0x14000fd55  mov     r12, [r14+8]
0x14000fd59  mov     rcx, r12
0x14000fd5c  sub     rcx, rdx
0x14000fd5f  lea     esi, [rdi+8]
0x14000fd62  cmp     rcx, rsi
0x14000fd65  jbe     short loc_14000FD6D
0x14000fd67  lea     rax, [rdx+8]
0x14000fd6b  jmp     short loc_14000FDA1
0x14000fd6d  jnb     short loc_14000FDA5
0x14000fd6f  mov     rax, [r14+10h]
0x14000fd73  sub     rax, rdx
0x14000fd76  cmp     rax, rsi
0x14000fd79  jnb     short loc_14000FD8D
0x14000fd7b  lea     r8, [rsp+118h+arg_0]
0x14000fd83  mov     rcx, r14
0x14000fd86  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x14000fd8b  jmp     short loc_14000FDA5
0x14000fd8d  sub     rsi, rcx
0x14000fd90  mov     r8, rsi; Size
0x14000fd93  xor     edx, edx; Val
0x14000fd95  mov     rcx, r12; void *
0x14000fd98  call    memset_0
0x14000fd9d  lea     rax, [rsi+r12]
0x14000fda1  mov     [r14+8], rax
0x14000fda5  mov     rsi, [r14]
0x14000fda8  mov     [rsp+118h+var_58], rsi
0x14000fdb0  xor     r9d, r9d; lpName
0x14000fdb3  xor     r8d, r8d; bInitialState
0x14000fdb6  lea     edx, [r9+1]; bManualReset
0x14000fdba  xor     ecx, ecx; lpEventAttributes
0x14000fdbc  call    cs:__imp_CreateEventW
0x14000fdc2  mov     r14, rax
0x14000fdc5  mov     [rsp+118h+var_88], rax
0x14000fdcd  test    rax, rax
0x14000fdd0  jnz     short loc_14000FDDC
0x14000fdd2  mov     esi, 80070008h
0x14000fdd7  jmp     loc_14000FF1D
0x14000fddc  mov     eax, [r15]
0x14000fddf  mov     [rsi], eax
0x14000fde1  lea     r8, [rsp+118h+var_58]
0x14000fde9  lea     rdx, [rsp+118h+var_88]
0x14000fdf1  lea     rcx, [rsp+118h+var_70]
0x14000fdf9  call    ??$Make@VToastFeedback@@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VToastFeedback@@@12@AEAPEAXAEAPEAUSendNotificationOperationResult@@@Z; Microsoft::WRL::Details::Make<ToastFeedback,void * &,SendNotificationOperationResult * &>(void * &,SendNotificationOperationResult * &)
0x14000fdfe  mov     rsi, [rax]
0x14000fe01  mov     [rax], rdi
0x14000fe04  test    rsi, rsi
0x14000fe07  jz      short loc_14000FE23
0x14000fe09  mov     rax, [rsi]
0x14000fe0c  mov     rcx, rsi
0x14000fe0f  mov     rax, [rax+8]
0x14000fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe18  mov     rbx, rsi
0x14000fe1b  mov     [rsp+118h+var_68], rbx
0x14000fe23  mov     rcx, [rsp+118h+var_70]
0x14000fe2b  test    rcx, rcx
0x14000fe2e  jz      short loc_14000FE45
0x14000fe30  mov     [rsp+118h+var_70], rdi
0x14000fe38  mov     rax, [rcx]
0x14000fe3b  mov     rax, [rax+10h]
0x14000fe3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe44  nop
0x14000fe45  mov     r10, [rsp+118h+var_78]
0x14000fe4d  movsd   xmm0, [rsp+118h+var_48]
0x14000fe56  movsd   [rsp+118h+var_58], xmm0
0x14000fe5f  mov     eax, [rsp+118h+var_40]
0x14000fe66  mov     [rsp+118h+var_50], eax
0x14000fe6d  mov     rax, [r10]
0x14000fe70  lea     rcx, [r15+4]
0x14000fe74  lea     r9, [r15+216h]
0x14000fe7b  lea     rdx, [r15+16h]
0x14000fe7f  lea     r8, [rsp+118h+arg_8]
0x14000fe87  mov     [rsp+118h+var_A0], r8
0x14000fe8c  mov     [rsp+118h+var_A8], edi
0x14000fe90  mov     [rsp+118h+var_B0], rdi
0x14000fe95  mov     [rsp+118h+var_B8], rbx
0x14000fe9a  mov     [rsp+118h+var_C0], rdi
0x14000fe9f  mov     [rsp+118h+var_C8], edi
0x14000fea3  mov     [rsp+118h+var_D0], edi
0x14000fea7  lea     r8, [rsp+118h+var_58]
0x14000feaf  mov     [rsp+118h+var_D8], r8
0x14000feb4  mov     [rsp+118h+var_E0], rdi
0x14000feb9  mov     [rsp+118h+var_E8], rcx
0x14000febe  mov     [rsp+118h+var_F0], r9
0x14000fec3  mov     dword ptr [rsp+118h+ppv], 1
0x14000fecb  xor     r9d, r9d
0x14000fece  mov     r8, r13
0x14000fed1  mov     rcx, r10
0x14000fed4  mov     rax, [rax+40h]
0x14000fed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fedd  mov     esi, eax
0x14000fedf  test    eax, eax
0x14000fee1  js      short loc_14000FF1D
0x14000fee3  mov     edx, 7530h; dwMilliseconds
0x14000fee8  mov     rcx, r14; hHandle
0x14000feeb  call    cs:__imp_WaitForSingleObject
0x14000fef1  test    eax, eax
0x14000fef3  jz      short loc_14000FF1D
0x14000fef5  mov     esi, 800705B4h
0x14000fefa  jmp     short loc_14000FF1D
0x14000fefc  xor     edi, edi
0x14000fefe  mov     esi, [rsp+118h+arg_0]
0x14000ff05  mov     rbx, [rsp+118h+var_68]
0x14000ff0d  mov     r14, [rsp+118h+var_88]
0x14000ff15  mov     r15, [rsp+118h+var_58]
0x14000ff1d  test    r14, r14
0x14000ff20  jz      short loc_14000FF2B
0x14000ff22  mov     rcx, r14; hObject
0x14000ff25  call    cs:__imp_CloseHandle
0x14000ff2b  lea     rax, WPP_GLOBAL_Control
0x14000ff32  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff39  cmp     rcx, rax
0x14000ff3c  jz      short loc_14000FF60
0x14000ff3e  cmp     byte ptr [rcx+19h], 4
0x14000ff42  jb      short loc_14000FF60
0x14000ff44  test    byte ptr [rcx+1Ch], 1
0x14000ff48  jz      short loc_14000FF60
0x14000ff4a  lea     r9, [r15+4]
0x14000ff4e  mov     edx, 18h
0x14000ff53  mov     dword ptr [rsp+118h+ppv], esi
0x14000ff57  mov     rcx, [rcx+10h]
0x14000ff5b  call    WPP_SF_SD
0x14000ff60  test    esi, esi
0x14000ff62  js      short loc_14000FF68
0x14000ff64  mov     esi, edi
0x14000ff66  jmp     short loc_14000FF79
0x14000ff68  mov     eax, esi
0x14000ff6a  and     eax, 1FFF0000h
0x14000ff6f  cmp     eax, 70000h
0x14000ff74  jnz     short loc_14000FF79
0x14000ff76  movzx   esi, si
0x14000ff79  test    rbx, rbx
0x14000ff7c  jz      short loc_14000FF8E
0x14000ff7e  mov     rax, [rbx]
0x14000ff81  mov     rcx, rbx
0x14000ff84  mov     rax, [rax+10h]
0x14000ff88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff8d  nop
0x14000ff8e  mov     rcx, [rsp+118h+var_80]
0x14000ff96  test    rcx, rcx
0x14000ff99  jz      short loc_14000FFA8
0x14000ff9b  mov     rax, [rcx]
0x14000ff9e  mov     rax, [rax+10h]
0x14000ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffa7  nop
0x14000ffa8  mov     rcx, [rsp+118h+var_78]
0x14000ffb0  test    rcx, rcx
0x14000ffb3  jz      short loc_14000FFC2
0x14000ffb5  mov     rax, [rcx]
0x14000ffb8  mov     rax, [rax+10h]
0x14000ffbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffc1  nop
0x14000ffc2  mov     rcx, [rsp+118h+arg_18]
0x14000ffca  test    rcx, rcx
0x14000ffcd  jz      short loc_14000FFDC
0x14000ffcf  mov     rdx, [rcx]
0x14000ffd2  mov     rax, [rdx+10h]
0x14000ffd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffdb  nop
0x14000ffdc  mov     eax, esi
0x14000ffde  add     rsp, 0E0h
0x14000ffe5  pop     r15
0x14000ffe7  pop     r14
0x14000ffe9  pop     r13
0x14000ffeb  pop     r12
0x14000ffed  pop     rdi
0x14000ffee  pop     rsi
0x14000ffef  pop     rbx
0x14000fff0  retn
```
