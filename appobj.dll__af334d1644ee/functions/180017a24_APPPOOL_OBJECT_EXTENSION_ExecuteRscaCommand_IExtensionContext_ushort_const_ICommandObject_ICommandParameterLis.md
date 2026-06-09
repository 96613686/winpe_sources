# APPPOOL_OBJECT_EXTENSION::ExecuteRscaCommand(IExtensionContext *,ushort const *,ICommandObject *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180017a24`
- end: `0x180017f86`
- name: `?ExecuteRscaCommand@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandObject@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1378`
- prototype: `__int64 __fastcall(APPPOOL_OBJECT_EXTENSION *this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017f90`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180004a70`
- `0x18000557c`
- `0x180006b6c`
- `0x180017a24`
- `0x180018490`
- `0x1800186e0`
- `0x18002b0cc`
- `0x18002b250`
- `0x18002bd3c`
- `0x18002be28`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017b12`
- `msvcrt!_wcsicmp` at `0x180017b26`
- `msvcrt!_wcsicmp` at `0x180017d14`
- `msvcrt!_wcsicmp` at `0x180017da4`
- `msvcrt!_wcsicmp` at `0x180017e5d`
- `msvcrt!_wcsicmp` at `0x180017b12`
- `msvcrt!_wcsicmp` at `0x180017b26`
- `msvcrt!_wcsicmp` at `0x180017d14`
- `msvcrt!_wcsicmp` at `0x180017da4`
- `msvcrt!_wcsicmp` at `0x180017e5d`

## pseudocode

```c
__int64 __fastcall APPPOOL_OBJECT_EXTENSION::ExecuteRscaCommand(
        APPPOOL_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandObject *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  int v8; // r15d
  unsigned int v9; // esi
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  APPPOOL_OBJECT_EXTENSION *v14; // r13
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *, int *, _QWORD); // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  DWORD v21; // esi
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  STATUS_OBJECT *v25; // rax
  const unsigned __int16 **v26; // rdi
  int v28; // [rsp+28h] [rbp-D8h]
  int v29; // [rsp+28h] [rbp-D8h]
  int v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  va_list v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  APPPOOL_OBJECT_EXTENSION *v40; // [rsp+80h] [rbp-80h]
  struct ICommandObjectList *v41; // [rsp+88h] [rbp-78h]
  _BYTE v42[32]; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B8h] [rbp-48h]
  __int16 v45; // [rsp+BCh] [rbp-44h]
  int v46; // [rsp+C0h] [rbp-40h]
  va_list Arguments[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h]
  __int16 v49; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v50[126]; // [rsp+E2h] [rbp-1Eh] BYREF

  v40 = this;
  v41 = a6;
  v8 = 1;
  v31 = 0;
  v9 = 0;
  v34 = 1;
  v48 = 0;
  v33 = 0;
  v35 = 0;
  *(_OWORD *)Arguments = 0;
  memset_0(v50, 0, sizeof(v50));
  v44 = 128;
  v45 = 256;
  v43 = &v49;
  v46 = 0;
  v49 = 0;
  v32 = 4;
  v37 = 0;
  v36 = 0;
  v39 = 0;
  v38 = 0;
  if ( !a2 || !a3 || !a4 || !a6 || !a5 )
  {
    v12 = -2147024809;
    goto LABEL_61;
  }
  if ( !_wcsicmp(a3, L"START") || !_wcsicmp(a3, L"STOP") )
  {
    v12 = APP_OBJECT_UTILS::PopBooleanParameter((APP_OBJECT_UTILS *)v11, a2, a5, L"wait", &v34, v28, 1);
    v11 = v12 + 0x80000000;
    if ( (int)v11 >= 0 && v12 != -2147023483 )
      goto LABEL_61;
    v8 = v34;
    if ( v34 )
    {
      v13 = APP_OBJECT_UTILS::PopDwordParameter((APP_OBJECT_UTILS *)v11, a2, a5, L"timeout", &v35, v29, v30);
      v11 = 0x80000000LL;
      v12 = v13;
      if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147023483 )
        goto LABEL_61;
      v9 = v35;
    }
  }
  v12 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v11, a2, a5);
  if ( v12 < 0 )
    goto LABEL_61;
  v14 = v40;
  if ( (int)APPPOOL_OBJECT_EXTENSION::InitializeRSCA(v40) < 0 )
  {
    v12 = -2147024846;
    v15 = 3221226496LL;
    v16 = 2147942450LL;
LABEL_17:
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
      a2,
      v16,
      v15,
      Arguments,
      0);
    goto LABEL_61;
  }
  v12 = (*(__int64 (__fastcall **)(struct ICommandObject *, const unsigned __int16 *, va_list *))(*(_QWORD *)a4 + 80LL))(
          a4,
          L"APPPOOL.NAME",
          &v33);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a4 + 48LL))(a4, &v37);
    if ( v12 >= 0 )
    {
      v17 = *(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *, int *, _QWORD))(*(_QWORD *)a2 + 88LL);
      v36 = 64;
      v12 = v17(a2, v37, L"processModel.shutdownTimeLimit", &v49, &v36, 0);
      if ( v12 >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v42);
        v12 = TIMESPAN_PARSER::ParseFromString(&v39, v43);
        if ( v12 >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD, va_list, __int64 *))(**((_QWORD **)v14 + 6) + 32LL))(
                  *((_QWORD *)v14 + 6),
                  v33,
                  &v31);
          v12 = v18;
          if ( v18 < 0 )
          {
            v16 = 2147942405LL;
            if ( v18 == -2147024891 )
            {
              v15 = 3221226490LL;
              goto LABEL_17;
            }
            goto LABEL_61;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v31 + 24LL))(v31, &v32, &v38);
          if ( v12 < 0 )
            goto LABEL_61;
          if ( !_wcsicmp(a3, L"START") )
          {
            if ( !v9 )
              v9 = 30000;
            v19 = (*(__int64 (**)(void))(*(_QWORD *)v31 + 40LL))();
            v12 = v19;
            if ( v19 != -2147023835 || v32 )
            {
              v16 = 2147943456LL;
              if ( v19 == -2147023840 )
              {
                v15 = 3221226491LL;
                Arguments[0] = v33;
                goto LABEL_17;
              }
              if ( v19 < 0 )
                goto LABEL_61;
            }
            if ( v8 )
            {
              v12 = APPPOOL_OBJECT_EXTENSION::WaitForStateChange(v20, v31, 1, v9);
              if ( v12 < 0 )
                goto LABEL_61;
            }
            v21 = 1025;
LABEL_52:
            if ( v12 >= 0 )
            {
              v25 = (STATUS_OBJECT *)operator new(0x110u);
              if ( v25 && (v26 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v25)) != 0 )
              {
                Arguments[0] = v33;
                v12 = STATUS_OBJECT::Create(v26, v21, Arguments);
                if ( v12 >= 0 )
                  v12 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)v41 + 24LL))(
                          v41,
                          v26);
                (*((void (__fastcall **)(const unsigned __int16 **))*v26 + 2))(v26);
              }
              else
              {
                v12 = -2147024888;
              }
            }
            goto LABEL_61;
          }
          if ( !_wcsicmp(a3, L"STOP") )
          {
            if ( !v9 )
              v9 = 1000 * (v39 / 10000000) + 500;
            v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 48LL))(v31);
            v12 = v22;
            if ( v22 != -2147023835 || v32 != 2 )
            {
              v16 = 2147943462LL;
              if ( v22 == -2147023834 )
              {
                v15 = 3221226492LL;
                Arguments[0] = v33;
                goto LABEL_17;
              }
              if ( v22 < 0 )
                goto LABEL_61;
            }
            if ( v8 )
            {
              v12 = APPPOOL_OBJECT_EXTENSION::WaitForStateChange(v23, v31, 3, v9);
              if ( v12 < 0 )
                goto LABEL_61;
            }
            v21 = 1026;
            goto LABEL_52;
          }
          if ( _wcsicmp(a3, L"RECYCLE") )
          {
            v12 = -2147024846;
            goto LABEL_61;
          }
          v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 56LL))(v31);
          v16 = 2147946712LL;
          v12 = v24;
          if ( v24 == -2147020584 )
          {
            v15 = 3221226527LL;
            Arguments[0] = v33;
            goto LABEL_17;
          }
          v21 = 1027;
          if ( v24 >= 0 )
            goto LABEL_52;
        }
      }
    }
  }
LABEL_61:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v42);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180017a24  push    rbp
0x180017a26  push    rbx
0x180017a27  push    rsi
0x180017a28  push    rdi
0x180017a29  push    r12
0x180017a2b  push    r13
0x180017a2d  push    r14
0x180017a2f  push    r15
0x180017a31  lea     rbp, [rsp-78h]
0x180017a36  sub     rsp, 178h
0x180017a3d  mov     rax, cs:__security_cookie
0x180017a44  xor     rax, rsp
0x180017a47  mov     [rbp+0B0h+var_50], rax
0x180017a4b  mov     rbx, [rbp+0B0h+arg_28]
0x180017a52  xor     eax, eax
0x180017a54  mov     r13, [rbp+0B0h+arg_20]
0x180017a5b  mov     r14, r8
0x180017a5e  mov     rdi, rdx
0x180017a61  mov     [rbp+0B0h+var_130], rcx
0x180017a65  xorps   xmm0, xmm0
0x180017a68  mov     [rbp+0B0h+var_128], rbx
0x180017a6c  lea     r15d, [rax+1]
0x180017a70  mov     [rsp+1B0h+var_170], 0
0x180017a79  xor     esi, esi
0x180017a7b  mov     [rsp+1B0h+var_158], r15d
0x180017a80  xor     edx, edx; Val
0x180017a82  mov     [rbp+0B0h+var_D8], rax
0x180017a86  lea     r8d, [rax+7Eh]; Size
0x180017a8a  mov     [rsp+1B0h+var_160], rax
0x180017a8f  lea     rcx, [rbp+0B0h+var_CE]; void *
0x180017a93  mov     [rsp+1B0h+var_154], esi
0x180017a97  mov     r12, r9
0x180017a9a  movups  xmmword ptr [rbp+0B0h+Arguments], xmm0
0x180017a9e  call    memset_0
0x180017aa3  xor     ecx, ecx
0x180017aa5  mov     [rbp+0B0h+var_F8], 80h
0x180017aac  mov     [rbp+0B0h+var_F4], 100h
0x180017ab2  lea     rax, [rbp+0B0h+var_D0]
0x180017ab6  mov     [rbp+0B0h+var_100], rax
0x180017aba  mov     [rbp+0B0h+var_F0], ecx
0x180017abd  mov     [rbp+0B0h+var_D0], cx
0x180017ac1  mov     [rsp+1B0h+var_168], 4
0x180017ac9  mov     [rsp+1B0h+var_148], rcx
0x180017ace  mov     [rsp+1B0h+var_150], ecx
0x180017ad2  mov     [rsp+1B0h+var_138], rcx
0x180017ad7  mov     [rsp+1B0h+var_140], ecx
0x180017adb  test    rdi, rdi
0x180017ade  jz      loc_180017F18
0x180017ae4  test    r14, r14
0x180017ae7  jz      loc_180017F18
0x180017aed  test    r12, r12
0x180017af0  jz      loc_180017F18
0x180017af6  test    rbx, rbx
0x180017af9  jz      loc_180017F18
0x180017aff  test    r13, r13
0x180017b02  jz      loc_180017F18
0x180017b08  lea     rdx, aStart; "START"
0x180017b0f  mov     rcx, r14; String1
0x180017b12  call    cs:__imp__wcsicmp
0x180017b18  test    eax, eax
0x180017b1a  jz      short loc_180017B30
0x180017b1c  lea     rdx, aStop_0; "STOP"
0x180017b23  mov     rcx, r14; String1
0x180017b26  call    cs:__imp__wcsicmp
0x180017b2c  test    eax, eax
0x180017b2e  jnz     short loc_180017BAE
0x180017b30  lea     rax, [rsp+1B0h+var_158]
0x180017b35  mov     [rsp+1B0h+var_180], r15d; int
0x180017b3a  lea     r9, aWait; "wait"
0x180017b41  mov     [rsp+1B0h+var_190], rax; int *
0x180017b46  mov     r8, r13; struct ICommandParameterList *
0x180017b49  mov     rdx, rdi; struct IExtensionContext *
0x180017b4c  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x180017b51  mov     ebx, eax
0x180017b53  mov     eax, 80000000h
0x180017b58  lea     ecx, [rbx+rax]; this
0x180017b5b  test    eax, ecx
0x180017b5d  jnz     short loc_180017B6B
0x180017b5f  cmp     ebx, 80070585h
0x180017b65  jnz     loc_180017F1D
0x180017b6b  mov     r15d, [rsp+1B0h+var_158]
0x180017b70  test    r15d, r15d
0x180017b73  jz      short loc_180017BAE
0x180017b75  lea     rax, [rsp+1B0h+var_154]
0x180017b7a  mov     r8, r13; struct ICommandParameterList *
0x180017b7d  lea     r9, aTimeout; "timeout"
0x180017b84  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x180017b89  mov     rdx, rdi; struct IExtensionContext *
0x180017b8c  call    ?PopDwordParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAKHH@Z; APP_OBJECT_UTILS::PopDwordParameter(IExtensionContext *,ICommandParameterList *,ushort const *,ulong *,int,int)
0x180017b91  mov     ecx, 80000000h; this
0x180017b96  mov     ebx, eax
0x180017b98  add     eax, ecx
0x180017b9a  test    ecx, eax
0x180017b9c  jnz     short loc_180017BAA
0x180017b9e  cmp     ebx, 80070585h
0x180017ba4  jnz     loc_180017F1D
0x180017baa  mov     esi, [rsp+1B0h+var_154]
0x180017bae  mov     r8, r13; struct ICommandParameterList *
0x180017bb1  mov     rdx, rdi; struct IExtensionContext *
0x180017bb4  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180017bb9  mov     ebx, eax
0x180017bbb  test    eax, eax
0x180017bbd  js      loc_180017F1D
0x180017bc3  mov     r13, [rbp+0B0h+var_130]
0x180017bc7  mov     rcx, r13; this
0x180017bca  call    ?InitializeRSCA@APPPOOL_OBJECT_EXTENSION@@AEAAJXZ; APPPOOL_OBJECT_EXTENSION::InitializeRSCA(void)
0x180017bcf  test    eax, eax
0x180017bd1  jns     short loc_180017C03
0x180017bd3  mov     ebx, 80070032h
0x180017bd8  mov     r8d, 0C0000400h
0x180017bde  mov     edx, ebx
0x180017be0  mov     rax, [rdi]
0x180017be3  lea     r9, [rbp+0B0h+Arguments]
0x180017be7  mov     rcx, rdi
0x180017bea  mov     dword ptr [rsp+1B0h+var_190], 0
0x180017bf2  mov     rax, [rax+90h]
0x180017bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bfe  jmp     loc_180017F1D
0x180017c03  mov     rax, [r12]
0x180017c07  lea     r8, [rsp+1B0h+var_160]
0x180017c0c  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x180017c13  mov     rcx, r12
0x180017c16  mov     rax, [rax+50h]
0x180017c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c1f  mov     ebx, eax
0x180017c21  test    eax, eax
0x180017c23  js      loc_180017F1D
0x180017c29  mov     rax, [r12]
0x180017c2d  lea     rdx, [rsp+1B0h+var_148]
0x180017c32  mov     rcx, r12
0x180017c35  mov     rax, [rax+30h]
0x180017c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c3e  mov     ebx, eax
0x180017c40  test    eax, eax
0x180017c42  js      loc_180017F1D
0x180017c48  mov     rax, [rdi]
0x180017c4b  lea     rcx, [rsp+1B0h+var_150]
0x180017c50  mov     rdx, [rsp+1B0h+var_148]
0x180017c55  lea     r9, [rbp+0B0h+var_D0]
0x180017c59  mov     [rsp+1B0h+var_188], 0
0x180017c62  lea     r8, aProcessmodelSh; "processModel.shutdownTimeLimit"
0x180017c69  mov     [rsp+1B0h+var_190], rcx
0x180017c6e  mov     rcx, rdi
0x180017c71  mov     rax, [rax+58h]
0x180017c75  mov     [rsp+1B0h+var_150], 40h ; '@'
0x180017c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c82  mov     ebx, eax
0x180017c84  test    eax, eax
0x180017c86  js      loc_180017F1D
0x180017c8c  lea     rcx, [rbp+0B0h+var_120]; this
0x180017c90  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180017c95  mov     rdx, [rbp+0B0h+var_100]
0x180017c99  lea     rcx, [rsp+1B0h+var_138]
0x180017c9e  call    ?ParseFromString@TIMESPAN_PARSER@@QEAAJPEBGW4TIMESPAN_FORMAT@@H@Z; TIMESPAN_PARSER::ParseFromString(ushort const *,TIMESPAN_FORMAT,int)
0x180017ca3  mov     ebx, eax
0x180017ca5  test    eax, eax
0x180017ca7  js      loc_180017F1D
0x180017cad  mov     rcx, [r13+30h]
0x180017cb1  lea     r8, [rsp+1B0h+var_170]
0x180017cb6  mov     rdx, [rsp+1B0h+var_160]
0x180017cbb  mov     rax, [rcx]
0x180017cbe  mov     rax, [rax+20h]
0x180017cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cc7  mov     ebx, eax
0x180017cc9  test    eax, eax
0x180017ccb  jns     short loc_180017CE5
0x180017ccd  mov     edx, 80070005h
0x180017cd2  cmp     eax, edx
0x180017cd4  jnz     loc_180017F1D
0x180017cda  mov     r8d, 0C00003FAh
0x180017ce0  jmp     loc_180017BE0
0x180017ce5  mov     rcx, [rsp+1B0h+var_170]
0x180017cea  lea     r8, [rsp+1B0h+var_140]
0x180017cef  lea     rdx, [rsp+1B0h+var_168]
0x180017cf4  mov     rax, [rcx]
0x180017cf7  mov     rax, [rax+18h]
0x180017cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d00  mov     ebx, eax
0x180017d02  test    eax, eax
0x180017d04  js      loc_180017F1D
0x180017d0a  lea     rdx, aStart; "START"
0x180017d11  mov     rcx, r14; String1
0x180017d14  call    cs:__imp__wcsicmp
0x180017d1a  test    eax, eax
0x180017d1c  jnz     short loc_180017D9A
0x180017d1e  mov     rcx, [rsp+1B0h+var_170]
0x180017d23  mov     eax, 7530h
0x180017d28  test    esi, esi
0x180017d2a  cmovz   esi, eax
0x180017d2d  mov     rax, [rcx]
0x180017d30  mov     rax, [rax+28h]
0x180017d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d39  mov     ebx, eax
0x180017d3b  cmp     eax, 80070425h
0x180017d40  jnz     short loc_180017D49
0x180017d42  cmp     [rsp+1B0h+var_168], 0
0x180017d47  jz      short loc_180017D6E
0x180017d49  mov     edx, 80070420h
0x180017d4e  cmp     eax, edx
0x180017d50  jnz     short loc_180017D66
0x180017d52  mov     rax, [rsp+1B0h+var_160]
0x180017d57  mov     r8d, 0C00003FBh
0x180017d5d  mov     [rbp+0B0h+Arguments], rax
0x180017d61  jmp     loc_180017BE0
0x180017d66  test    eax, eax
0x180017d68  js      loc_180017F1D
0x180017d6e  test    r15d, r15d
0x180017d71  jz      short loc_180017D90
0x180017d73  mov     rdx, [rsp+1B0h+var_170]
0x180017d78  mov     r9d, esi
0x180017d7b  mov     r8d, 1
0x180017d81  call    ?WaitForStateChange@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAUIRSCA_AppPool@@W4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@K@Z; APPPOOL_OBJECT_EXTENSION::WaitForStateChange(IRSCA_AppPool *,__MIDL___MIDL_itf_rscaps_0000_0003_0001,ulong)
0x180017d86  mov     ebx, eax
0x180017d88  test    eax, eax
0x180017d8a  js      loc_180017F1D
0x180017d90  mov     esi, 401h
0x180017d95  jmp     loc_180017EA4
0x180017d9a  lea     rdx, aStop_0; "STOP"
0x180017da1  mov     rcx, r14; String1
0x180017da4  call    cs:__imp__wcsicmp
0x180017daa  test    eax, eax
0x180017dac  jnz     loc_180017E53
0x180017db2  test    esi, esi
0x180017db4  jnz     short loc_180017DE4
0x180017db6  mov     rax, 0D6BF94D5E57A42BDh
0x180017dc0  imul    [rsp+1B0h+var_138]
0x180017dc5  add     rdx, [rsp+1B0h+var_138]
0x180017dca  sar     rdx, 17h
0x180017dce  mov     rax, rdx
0x180017dd1  shr     rax, 3Fh
0x180017dd5  add     rdx, rax
0x180017dd8  imul    esi, edx, 3E8h
0x180017dde  add     esi, 1F4h
0x180017de4  mov     rcx, [rsp+1B0h+var_170]
0x180017de9  mov     rax, [rcx]
0x180017dec  mov     rax, [rax+30h]
0x180017df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df5  mov     ebx, eax
0x180017df7  cmp     eax, 80070425h
0x180017dfc  jnz     short loc_180017E05
0x180017dfe  cmp     [rsp+1B0h+var_168], 2
0x180017e03  jz      short loc_180017E2A
0x180017e05  mov     edx, 80070426h
0x180017e0a  cmp     eax, edx
0x180017e0c  jnz     short loc_180017E22
0x180017e0e  mov     rax, [rsp+1B0h+var_160]
0x180017e13  mov     r8d, 0C00003FCh
0x180017e19  mov     [rbp+0B0h+Arguments], rax
0x180017e1d  jmp     loc_180017BE0
0x180017e22  test    eax, eax
0x180017e24  js      loc_180017F1D
0x180017e2a  test    r15d, r15d
0x180017e2d  jz      short loc_180017E4C
0x180017e2f  mov     rdx, [rsp+1B0h+var_170]
0x180017e34  mov     r9d, esi
0x180017e37  mov     r8d, 3
0x180017e3d  call    ?WaitForStateChange@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAUIRSCA_AppPool@@W4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@K@Z; APPPOOL_OBJECT_EXTENSION::WaitForStateChange(IRSCA_AppPool *,__MIDL___MIDL_itf_rscaps_0000_0003_0001,ulong)
0x180017e42  mov     ebx, eax
0x180017e44  test    eax, eax
0x180017e46  js      loc_180017F1D
0x180017e4c  mov     esi, 402h
0x180017e51  jmp     short loc_180017EA4
0x180017e53  lea     rdx, aRecycle; "RECYCLE"
0x180017e5a  mov     rcx, r14; String1
0x180017e5d  call    cs:__imp__wcsicmp
0x180017e63  test    eax, eax
0x180017e65  jnz     loc_180017F11
0x180017e6b  mov     rcx, [rsp+1B0h+var_170]
0x180017e70  mov     rax, [rcx]
0x180017e73  mov     rax, [rax+38h]
0x180017e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e7c  mov     edx, 800710D8h
0x180017e81  mov     ebx, eax
0x180017e83  cmp     eax, edx
0x180017e85  jnz     short loc_180017E9B
0x180017e87  mov     rax, [rsp+1B0h+var_160]
0x180017e8c  mov     r8d, 0C000041Fh
0x180017e92  mov     [rbp+0B0h+Arguments], rax
0x180017e96  jmp     loc_180017BE0
0x180017e9b  mov     esi, 403h
0x180017ea0  test    eax, eax
0x180017ea2  js      short loc_180017F1D
0x180017ea4  test    ebx, ebx
0x180017ea6  js      short loc_180017F1D
0x180017ea8  mov     ecx, 110h; Size
0x180017ead  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017eb2  test    rax, rax
0x180017eb5  jz      short loc_180017F0A
0x180017eb7  mov     rcx, rax; this
0x180017eba  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180017ebf  mov     rdi, rax
0x180017ec2  test    rax, rax
0x180017ec5  jz      short loc_180017F0A
0x180017ec7  mov     rax, [rsp+1B0h+var_160]
0x180017ecc  lea     r8, [rbp+0B0h+Arguments]; Arguments
0x180017ed0  mov     edx, esi; dwMessageId
0x180017ed2  mov     [rbp+0B0h+Arguments], rax
0x180017ed6  mov     rcx, rdi; this
0x180017ed9  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180017ede  mov     ebx, eax
  ... truncated ...
```
