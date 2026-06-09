# PackagedStartupTask::FillValues(PackagedStartupTask &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternal>)

- ea: `0x1800d33d8`
- end: `0x1800d36cf`
- name: `?FillValues@PackagedStartupTask@@CAJAEAV1@V?$ComPtr@UIStartupTaskInternal@Internal@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d2254`
- `0x1800d245c`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x1800d33d8`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d346e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d34be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d34f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d356f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d35ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d35e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d346e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d34be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d34f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d356f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d35ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d35e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackagedStartupTask::FillValues(HSTRING *a1, int *a2)
{
  HSTRING v4; // rcx
  HSTRING v5; // rsi
  __int64 (__fastcall *v6)(HSTRING, HSTRING *); // rdi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HSTRING v10; // rsi
  __int64 (__fastcall *v11)(HSTRING, HSTRING *); // rdi
  HSTRING v12; // rsi
  __int64 (__fastcall *v13)(HSTRING, HSTRING *); // rdi
  HSTRING v14; // rsi
  __int64 (__fastcall *v15)(HSTRING, HSTRING *); // rdi
  HSTRING v16; // rsi
  __int64 (__fastcall *v17)(HSTRING, HSTRING *); // rdi
  HSTRING v18; // rsi
  __int64 (__fastcall *v19)(HSTRING, HSTRING *); // rdi
  HSTRING v20; // rsi
  __int64 (__fastcall *v21)(HSTRING, HSTRING *); // rdi
  HSTRING v22; // rsi
  __int64 (__fastcall *v23)(HSTRING, HSTRING *); // rdi
  char v24; // bl
  int v25; // edi
  __int64 v26; // rdx
  int v27; // ecx
  bool v28; // dl
  int v30[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v32; // [rsp+60h] [rbp+8h] BYREF
  int *v33; // [rsp+68h] [rbp+10h]
  int v34; // [rsp+70h] [rbp+18h] BYREF

  v33 = a2;
  v4 = 0;
  if ( v30 != a2 )
  {
    v4 = *(HSTRING *)a2;
    *(_QWORD *)a2 = 0;
  }
  *(_QWORD *)v30 = *a1;
  *a1 = v4;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v30);
  v34 = 0;
  v5 = *a1;
  v6 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 144LL);
  WindowsDeleteString(a1[3]);
  a1[3] = 0;
  v7 = v6(v5, a1 + 3);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 138;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v7,
      v30[0]);
    goto LABEL_31;
  }
  v10 = *a1;
  v11 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 64LL);
  WindowsDeleteString(a1[6]);
  a1[6] = 0;
  v7 = v11(v10, a1 + 6);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 140;
    goto LABEL_7;
  }
  v12 = *a1;
  v13 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 120LL);
  WindowsDeleteString(a1[5]);
  a1[5] = 0;
  v7 = v13(v12, a1 + 5);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 142;
    goto LABEL_7;
  }
  v14 = *a1;
  v15 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 72LL);
  WindowsDeleteString(a1[7]);
  a1[7] = 0;
  v7 = v15(v14, a1 + 7);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 144;
    goto LABEL_7;
  }
  v16 = *a1;
  v17 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 96LL);
  WindowsDeleteString(a1[4]);
  a1[4] = 0;
  v7 = v17(v16, a1 + 4);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 146;
    goto LABEL_7;
  }
  v18 = *a1;
  v19 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 112LL);
  WindowsDeleteString(a1[1]);
  a1[1] = 0;
  v7 = v19(v18, a1 + 1);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 148;
    goto LABEL_7;
  }
  v20 = *a1;
  v21 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 104LL);
  WindowsDeleteString(a1[2]);
  a1[2] = 0;
  v7 = v21(v20, a1 + 2);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 150;
    goto LABEL_7;
  }
  v22 = *a1;
  v23 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a1 + 88LL);
  WindowsDeleteString(a1[8]);
  a1[8] = 0;
  v7 = v23(v22, a1 + 8);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 152;
    goto LABEL_7;
  }
  v24 = 1;
  v32 = 1;
  v25 = (*(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)*a1 + 160LL))(*a1, &v32);
  if ( v25 < 0 )
  {
    v26 = 155;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v25,
      v30[0]);
    v8 = v25;
    goto LABEL_31;
  }
  v25 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)*a1 + 128LL))(*a1, &v34);
  if ( v25 < 0 )
  {
    v26 = 157;
    goto LABEL_22;
  }
  v27 = v34;
  v28 = ((v34 - 2) & 0xFFFFFFFD) == 0;
  *((_BYTE *)a1 + 72) = v28;
  if ( !v32 || (unsigned int)(v27 - 3) <= 1 )
    v24 = 0;
  *((_BYTE *)a1 + 73) = v24;
  if ( !v28 )
    (*(void (__fastcall **)(HSTRING, __int64))(*(_QWORD *)*a1 + 56LL))(*a1, (__int64)a1 + 76);
  v8 = 0;
LABEL_31:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
  return v8;
}

```

## disassembly

```asm
0x1800d33d8  mov     [rsp+arg_8], rdx
0x1800d33dd  push    rbx
0x1800d33de  push    rsi
0x1800d33df  push    rdi
0x1800d33e0  push    r14
0x1800d33e2  push    r15
0x1800d33e4  sub     rsp, 30h
0x1800d33e8  mov     r15, rdx
0x1800d33eb  mov     r14, rcx
0x1800d33ee  xor     ecx, ecx
0x1800d33f0  lea     rax, [rsp+58h+var_38]
0x1800d33f5  cmp     rax, rdx
0x1800d33f8  jz      short loc_1800D3404
0x1800d33fa  mov     rcx, [rdx]
0x1800d33fd  mov     qword ptr [rdx], 0
0x1800d3404  mov     rax, [r14]
0x1800d3407  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800d340c  mov     [r14], rcx
0x1800d340f  lea     rcx, [rsp+58h+var_38]
0x1800d3414  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800d3419  mov     [rsp+58h+arg_10], 0
0x1800d3421  mov     rsi, [r14]
0x1800d3424  mov     rax, [rsi]
0x1800d3427  mov     rdi, [rax+90h]
0x1800d342e  lea     rbx, [r14+18h]
0x1800d3432  mov     rcx, [rbx]; string
0x1800d3435  call    cs:__imp_WindowsDeleteString
0x1800d343b  mov     qword ptr [rbx], 0
0x1800d3442  mov     rdx, rbx
0x1800d3445  mov     rcx, rsi
0x1800d3448  mov     rax, rdi
0x1800d344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3450  mov     ebx, eax
0x1800d3452  test    eax, eax
0x1800d3454  jns     short loc_1800D345D
0x1800d3456  mov     edx, 8Ah
0x1800d345b  jmp     short loc_1800D3494
0x1800d345d  mov     rsi, [r14]
0x1800d3460  mov     rax, [rsi]
0x1800d3463  mov     rdi, [rax+40h]
0x1800d3467  lea     rbx, [r14+30h]
0x1800d346b  mov     rcx, [rbx]; string
0x1800d346e  call    cs:__imp_WindowsDeleteString
0x1800d3474  mov     qword ptr [rbx], 0
0x1800d347b  mov     rdx, rbx
0x1800d347e  mov     rcx, rsi
0x1800d3481  mov     rax, rdi
0x1800d3484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3489  mov     ebx, eax
0x1800d348b  test    eax, eax
0x1800d348d  jns     short loc_1800D34AD
0x1800d348f  mov     edx, 8Ch; void *
0x1800d3494  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d349b  mov     r9d, eax; char *
0x1800d349e  mov     rcx, [rsp+58h]; this
0x1800d34a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d34a8  jmp     loc_1800D36B9
0x1800d34ad  mov     rsi, [r14]
0x1800d34b0  mov     rax, [rsi]
0x1800d34b3  mov     rdi, [rax+78h]
0x1800d34b7  lea     rbx, [r14+28h]
0x1800d34bb  mov     rcx, [rbx]; string
0x1800d34be  call    cs:__imp_WindowsDeleteString
0x1800d34c4  mov     qword ptr [rbx], 0
0x1800d34cb  mov     rdx, rbx
0x1800d34ce  mov     rcx, rsi
0x1800d34d1  mov     rax, rdi
0x1800d34d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d34d9  mov     ebx, eax
0x1800d34db  test    eax, eax
0x1800d34dd  jns     short loc_1800D34E6
0x1800d34df  mov     edx, 8Eh
0x1800d34e4  jmp     short loc_1800D3494
0x1800d34e6  mov     rsi, [r14]
0x1800d34e9  mov     rax, [rsi]
0x1800d34ec  mov     rdi, [rax+48h]
0x1800d34f0  lea     rbx, [r14+38h]
0x1800d34f4  mov     rcx, [rbx]; string
0x1800d34f7  call    cs:__imp_WindowsDeleteString
0x1800d34fd  mov     qword ptr [rbx], 0
0x1800d3504  mov     rdx, rbx
0x1800d3507  mov     rcx, rsi
0x1800d350a  mov     rax, rdi
0x1800d350d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3512  mov     ebx, eax
0x1800d3514  test    eax, eax
0x1800d3516  jns     short loc_1800D3522
0x1800d3518  mov     edx, 90h
0x1800d351d  jmp     loc_1800D3494
0x1800d3522  mov     rsi, [r14]
0x1800d3525  mov     rax, [rsi]
0x1800d3528  mov     rdi, [rax+60h]
0x1800d352c  lea     rbx, [r14+20h]
0x1800d3530  mov     rcx, [rbx]; string
0x1800d3533  call    cs:__imp_WindowsDeleteString
0x1800d3539  mov     qword ptr [rbx], 0
0x1800d3540  mov     rdx, rbx
0x1800d3543  mov     rcx, rsi
0x1800d3546  mov     rax, rdi
0x1800d3549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d354e  mov     ebx, eax
0x1800d3550  test    eax, eax
0x1800d3552  jns     short loc_1800D355E
0x1800d3554  mov     edx, 92h
0x1800d3559  jmp     loc_1800D3494
0x1800d355e  mov     rsi, [r14]
0x1800d3561  mov     rax, [rsi]
0x1800d3564  mov     rdi, [rax+70h]
0x1800d3568  lea     rbx, [r14+8]
0x1800d356c  mov     rcx, [rbx]; string
0x1800d356f  call    cs:__imp_WindowsDeleteString
0x1800d3575  mov     qword ptr [rbx], 0
0x1800d357c  mov     rdx, rbx
0x1800d357f  mov     rcx, rsi
0x1800d3582  mov     rax, rdi
0x1800d3585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d358a  mov     ebx, eax
0x1800d358c  test    eax, eax
0x1800d358e  jns     short loc_1800D359A
0x1800d3590  mov     edx, 94h
0x1800d3595  jmp     loc_1800D3494
0x1800d359a  mov     rsi, [r14]
0x1800d359d  mov     rax, [rsi]
0x1800d35a0  mov     rdi, [rax+68h]
0x1800d35a4  lea     rbx, [r14+10h]
0x1800d35a8  mov     rcx, [rbx]; string
0x1800d35ab  call    cs:__imp_WindowsDeleteString
0x1800d35b1  mov     qword ptr [rbx], 0
0x1800d35b8  mov     rdx, rbx
0x1800d35bb  mov     rcx, rsi
0x1800d35be  mov     rax, rdi
0x1800d35c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d35c6  mov     ebx, eax
0x1800d35c8  test    eax, eax
0x1800d35ca  jns     short loc_1800D35D6
0x1800d35cc  mov     edx, 96h
0x1800d35d1  jmp     loc_1800D3494
0x1800d35d6  mov     rsi, [r14]
0x1800d35d9  mov     rax, [rsi]
0x1800d35dc  mov     rdi, [rax+58h]
0x1800d35e0  lea     rbx, [r14+40h]
0x1800d35e4  mov     rcx, [rbx]; string
0x1800d35e7  call    cs:__imp_WindowsDeleteString
0x1800d35ed  mov     qword ptr [rbx], 0
0x1800d35f4  mov     rdx, rbx
0x1800d35f7  mov     rcx, rsi
0x1800d35fa  mov     rax, rdi
0x1800d35fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3602  mov     ebx, eax
0x1800d3604  test    eax, eax
0x1800d3606  jns     short loc_1800D3612
0x1800d3608  mov     edx, 98h
0x1800d360d  jmp     loc_1800D3494
0x1800d3612  mov     ebx, 1
0x1800d3617  mov     [rsp+58h+arg_0], bl
0x1800d361b  mov     rcx, [r14]
0x1800d361e  mov     rax, [rcx]
0x1800d3621  lea     rdx, [rsp+58h+arg_0]
0x1800d3626  mov     rax, [rax+0A0h]
0x1800d362d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3632  mov     edi, eax
0x1800d3634  test    eax, eax
0x1800d3636  jns     short loc_1800D3655
0x1800d3638  mov     edx, 9Bh; void *
0x1800d363d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d3644  mov     r9d, edi; char *
0x1800d3647  mov     rcx, [rsp+58h]; this
0x1800d364c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3651  mov     ebx, edi
0x1800d3653  jmp     short loc_1800D36B9
0x1800d3655  mov     rcx, [r14]
0x1800d3658  mov     rax, [rcx]
0x1800d365b  lea     rdx, [rsp+58h+arg_10]
0x1800d3660  mov     rax, [rax+80h]
0x1800d3667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d366c  mov     edi, eax
0x1800d366e  test    eax, eax
0x1800d3670  jns     short loc_1800D3679
0x1800d3672  mov     edx, 9Dh
0x1800d3677  jmp     short loc_1800D363D
0x1800d3679  mov     ecx, [rsp+58h+arg_10]
0x1800d367d  lea     eax, [rcx-2]
0x1800d3680  test    eax, 0FFFFFFFDh
0x1800d3685  setz    dl
0x1800d3688  mov     [r14+48h], dl
0x1800d368c  cmp     [rsp+58h+arg_0], 0
0x1800d3691  jz      short loc_1800D369A
0x1800d3693  lea     eax, [rcx-3]
0x1800d3696  cmp     eax, ebx
0x1800d3698  ja      short loc_1800D369C
0x1800d369a  xor     bl, bl
0x1800d369c  mov     [r14+49h], bl
0x1800d36a0  test    dl, dl
0x1800d36a2  jnz     short loc_1800D36B7
0x1800d36a4  mov     rcx, [r14]
0x1800d36a7  mov     rax, [rcx]
0x1800d36aa  lea     rdx, [r14+4Ch]
0x1800d36ae  mov     rax, [rax+38h]
0x1800d36b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d36b7  xor     ebx, ebx
0x1800d36b9  mov     rcx, r15
0x1800d36bc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800d36c1  mov     eax, ebx
0x1800d36c3  add     rsp, 30h
0x1800d36c7  pop     r15
0x1800d36c9  pop     r14
0x1800d36cb  pop     rdi
0x1800d36cc  pop     rsi
0x1800d36cd  pop     rbx
0x1800d36ce  retn
```
