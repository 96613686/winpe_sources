# CONFIG_OBJECT_EXTENSION::DoClear(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180019948`
- end: `0x180019d29`
- name: `?DoClear@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *this, struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`
- `0x18001bd50`
- `0x18001ca1c`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180004a70`
- `0x18000557c`
- `0x180006b6c`
- `0x180018868`
- `0x180019948`
- `0x18002b0cc`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180019a28`: `delete`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::DoClear(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  const unsigned __int16 **v8; // rdi
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // ebx
  va_list v12; // r12
  CONFIG_OBJECT_EXTENSION *v13; // rcx
  unsigned int v14; // eax
  STATUS_OBJECT *v15; // rax
  const unsigned __int16 **v16; // rax
  unsigned int i; // r14d
  int v19; // [rsp+28h] [rbp-D8h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  struct ICommandObjectList *v28; // [rsp+80h] [rbp-80h]
  va_list Arguments[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[32]; // [rsp+98h] [rbp-68h] BYREF
  _WORD *v31; // [rsp+B8h] [rbp-48h]
  int v32; // [rsp+C0h] [rbp-40h]
  __int16 v33; // [rsp+C4h] [rbp-3Ch]
  int v34; // [rsp+C8h] [rbp-38h]
  __int16 v35; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v36[510]; // [rsp+D2h] [rbp-2Eh] BYREF

  v28 = a6;
  v20 = 0;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  v21 = 0;
  v8 = 0;
  v22 = 0;
  v25 = 0;
  *(_OWORD *)Arguments = 0;
  memset_0(v36, 0, sizeof(v36));
  v32 = 512;
  v31 = &v35;
  v33 = 256;
  v34 = 0;
  v35 = 0;
  v23 = 0;
  if ( !a2 || !a4 || !a3 || !a5 )
  {
    v11 = -2147024809;
    goto LABEL_30;
  }
  v11 = APP_OBJECT_UTILS::PopBooleanParameter(v10, a2, a5, L"delete", &v23, v19, 1);
  if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023483 )
  {
    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int16 *, __int64))(*(_QWORD *)a2 + 72LL))(
            a2,
            a3,
            &v35,
            256);
    if ( v11 >= 0 )
    {
      STRU::SyncWithBuffer((STRU *)v30);
      v12 = (va_list)v31;
      v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, _WORD *, __int64 *))(*(_QWORD *)a2 + 80LL))(
              a2,
              v31,
              &v24);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, va_list, __int64 *, __int64 *))(*(_QWORD *)v24 + 88LL))(
                v24,
                v12,
                &v25,
                &v22);
        if ( v11 < 0
          || (v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **, __int64 *))(*(_QWORD *)v25 + 64LL))(
                      v25,
                      a4,
                      a3,
                      &v21,
                      &v22),
              v11 < 0) )
        {
          if ( v22 )
            (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
              a2,
              (unsigned int)v11,
              &Str,
              v22,
              0);
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)a5 + 24LL))(
                  a5,
                  &v20);
          if ( v11 < 0 )
            goto LABEL_30;
          v14 = v20;
          if ( v20 )
          {
            for ( i = 0; i < v14; ++i )
            {
              v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, __int64 *, __int64 *))(*(_QWORD *)a5 + 32LL))(
                      a5,
                      i,
                      &v26,
                      &v27);
              if ( v11 < 0 )
                goto LABEL_30;
              v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, __int64))(*(_QWORD *)a2 + 104LL))(
                      a2,
                      v21,
                      v26);
              if ( v11 < 0 )
                goto LABEL_30;
              v14 = v20;
            }
          }
          else
          {
            v11 = CONFIG_OBJECT_EXTENSION::ClearSection(v13, v21);
            if ( v11 < 0 )
              goto LABEL_30;
            if ( v23 )
            {
              v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 168LL))(v21);
              if ( v11 < 0 )
                goto LABEL_30;
            }
          }
          v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, va_list, _QWORD))(*(_QWORD *)a2 + 208LL))(
                  a2,
                  v12,
                  0);
          if ( v11 >= 0 )
          {
            v15 = (STATUS_OBJECT *)operator new(0x110u);
            if ( v15 && (v16 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v15), (v8 = v16) != 0) )
            {
              Arguments[0] = (va_list)a4;
              Arguments[1] = v12;
              v11 = STATUS_OBJECT::Create(v16, 0x409u, Arguments);
              if ( v11 >= 0 )
                v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)v28 + 24LL))(
                        v28,
                        v8);
            }
            else
            {
              v11 = -2147024888;
            }
          }
        }
      }
    }
  }
LABEL_30:
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v8 )
    (*((void (__fastcall **)(const unsigned __int16 **))*v8 + 2))(v8);
  BUFFER::~BUFFER((BUFFER *)v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019948  mov     [rsp-8+arg_0], rbx
0x18001994d  push    rbp
0x18001994e  push    rsi
0x18001994f  push    rdi
0x180019950  push    r12
0x180019952  push    r13
0x180019954  push    r14
0x180019956  push    r15
0x180019958  lea     rbp, [rsp-1E0h]
0x180019960  sub     rsp, 2E0h
0x180019967  mov     rax, cs:__security_cookie
0x18001996e  xor     rax, rsp
0x180019971  mov     [rbp+210h+var_40], rax
0x180019978  mov     rax, [rbp+210h+arg_28]
0x18001997f  lea     rcx, [rbp+210h+var_23E]; void *
0x180019983  mov     r15, [rbp+210h+arg_20]
0x18001998a  xor     r12d, r12d
0x18001998d  mov     r14, r8
0x180019990  mov     [rbp+210h+var_290], rax
0x180019994  mov     rsi, rdx
0x180019997  mov     [rsp+310h+var_2D0], r12d
0x18001999c  xorps   xmm0, xmm0
0x18001999f  mov     [rsp+310h+var_2A0], r12
0x1800199a4  xor     edx, edx; Val
0x1800199a6  mov     [rsp+310h+var_298], r12
0x1800199ab  mov     r8d, 1FEh; Size
0x1800199b1  mov     [rsp+310h+var_2B0], r12
0x1800199b6  mov     [rsp+310h+var_2C8], r12
0x1800199bb  mov     edi, r12d
0x1800199be  mov     [rsp+310h+var_2C0], r12
0x1800199c3  mov     r13, r9
0x1800199c6  mov     [rsp+310h+var_2A8], r12
0x1800199cb  movups  xmmword ptr [rbp+210h+Arguments], xmm0
0x1800199cf  call    memset_0
0x1800199d4  mov     [rbp+210h+var_250], 200h
0x1800199db  lea     rax, [rbp+210h+var_240]
0x1800199df  mov     [rbp+210h+var_258], rax
0x1800199e3  mov     [rbp+210h+var_24C], 100h
0x1800199e9  mov     [rbp+210h+var_248], r12d
0x1800199ed  mov     [rbp+210h+var_240], r12w
0x1800199f2  mov     [rsp+310h+var_2B8], r12d
0x1800199f7  test    rsi, rsi
0x1800199fa  jz      loc_180019C6D
0x180019a00  test    r13, r13
0x180019a03  jz      loc_180019C6D
0x180019a09  test    r14, r14
0x180019a0c  jz      loc_180019C6D
0x180019a12  test    r15, r15
0x180019a15  jz      loc_180019C6D
0x180019a1b  lea     rax, [rsp+310h+var_2B8]
0x180019a20  mov     [rsp+310h+var_2E0], 1; int
0x180019a28  lea     r9, aDelete; "delete"
0x180019a2f  mov     [rsp+310h+var_2F0], rax; int *
0x180019a34  mov     r8, r15; struct ICommandParameterList *
0x180019a37  mov     rdx, rsi; struct IExtensionContext *
0x180019a3a  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x180019a3f  mov     ebx, eax
0x180019a41  mov     eax, 80000000h
0x180019a46  lea     ecx, [rbx+rax]
0x180019a49  test    eax, ecx
0x180019a4b  jnz     short loc_180019A59
0x180019a4d  cmp     ebx, 80070585h
0x180019a53  jnz     loc_180019C72
0x180019a59  mov     rax, [rsi]
0x180019a5c  lea     r8, [rbp+210h+var_240]
0x180019a60  mov     r9d, 100h
0x180019a66  mov     rdx, r14
0x180019a69  mov     rcx, rsi
0x180019a6c  mov     rax, [rax+48h]
0x180019a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a75  mov     ebx, eax
0x180019a77  test    eax, eax
0x180019a79  js      loc_180019C72
0x180019a7f  lea     rcx, [rbp+210h+var_278]; this
0x180019a83  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180019a88  mov     rax, [rsi]
0x180019a8b  lea     r8, [rsp+310h+var_2B0]
0x180019a90  mov     r12, [rbp+210h+var_258]
0x180019a94  mov     rcx, rsi
0x180019a97  mov     rdx, r12
0x180019a9a  mov     rax, [rax+50h]
0x180019a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aa3  mov     ebx, eax
0x180019aa5  test    eax, eax
0x180019aa7  js      loc_180019C72
0x180019aad  mov     rcx, [rsp+310h+var_2B0]
0x180019ab2  lea     r9, [rsp+310h+var_2C0]
0x180019ab7  lea     r8, [rsp+310h+var_2A8]
0x180019abc  mov     rdx, r12
0x180019abf  mov     rax, [rcx]
0x180019ac2  mov     rax, [rax+58h]
0x180019ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019acb  mov     ebx, eax
0x180019acd  test    eax, eax
0x180019acf  jns     short loc_180019B03
0x180019ad1  mov     rcx, [rsp+310h+var_2C0]
0x180019ad6  test    rcx, rcx
0x180019ad9  jz      loc_180019C72
0x180019adf  mov     rax, [rsi]
0x180019ae2  lea     r8, Str
0x180019ae9  mov     r9, rcx
0x180019aec  mov     dword ptr [rsp+310h+var_2F0], edi
0x180019af0  mov     edx, ebx
0x180019af2  mov     rcx, rsi
0x180019af5  mov     rax, [rax+70h]
0x180019af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019afe  jmp     loc_180019C72
0x180019b03  mov     rcx, [rsp+310h+var_2A8]
0x180019b08  lea     rdx, [rsp+310h+var_2C0]
0x180019b0d  mov     [rsp+310h+var_2F0], rdx
0x180019b12  lea     r9, [rsp+310h+var_2C8]
0x180019b17  mov     r8, r14
0x180019b1a  mov     rdx, r13
0x180019b1d  mov     rax, [rcx]
0x180019b20  mov     rax, [rax+40h]
0x180019b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b29  mov     ebx, eax
0x180019b2b  test    eax, eax
0x180019b2d  js      short loc_180019AD1
0x180019b2f  mov     rax, [r15]
0x180019b32  lea     rdx, [rsp+310h+var_2D0]
0x180019b37  mov     rcx, r15
0x180019b3a  mov     rax, [rax+18h]
0x180019b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b43  mov     ebx, eax
0x180019b45  test    eax, eax
0x180019b47  js      loc_180019C72
0x180019b4d  mov     eax, [rsp+310h+var_2D0]
0x180019b51  test    eax, eax
0x180019b53  jnz     loc_180019C10
0x180019b59  mov     rdx, [rsp+310h+var_2C8]; struct INativeConfigurationElement *
0x180019b5e  call    ?ClearSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElement@@@Z; CONFIG_OBJECT_EXTENSION::ClearSection(INativeConfigurationElement *)
0x180019b63  mov     ebx, eax
0x180019b65  test    eax, eax
0x180019b67  js      loc_180019C72
0x180019b6d  cmp     [rsp+310h+var_2B8], edi
0x180019b71  jz      short loc_180019B91
0x180019b73  mov     rcx, [rsp+310h+var_2C8]
0x180019b78  mov     rax, [rcx]
0x180019b7b  mov     rax, [rax+0A8h]
0x180019b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b87  mov     ebx, eax
0x180019b89  test    eax, eax
0x180019b8b  js      loc_180019C72
0x180019b91  mov     rax, [rsi]
0x180019b94  xor     r8d, r8d
0x180019b97  mov     rdx, r12
0x180019b9a  mov     rcx, rsi
0x180019b9d  mov     rax, [rax+0D0h]
0x180019ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ba9  mov     ebx, eax
0x180019bab  test    eax, eax
0x180019bad  js      loc_180019C72
0x180019bb3  mov     ecx, 110h; Size
0x180019bb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019bbd  test    rax, rax
0x180019bc0  jz      loc_180019C66
0x180019bc6  mov     rcx, rax; this
0x180019bc9  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180019bce  mov     rdi, rax
0x180019bd1  test    rax, rax
0x180019bd4  jz      loc_180019C66
0x180019bda  lea     r8, [rbp+210h+Arguments]; Arguments
0x180019bde  mov     [rbp+210h+Arguments], r13
0x180019be2  mov     edx, 409h; dwMessageId
0x180019be7  mov     [rbp+210h+Arguments+8], r12
0x180019beb  mov     rcx, rax; this
0x180019bee  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180019bf3  mov     ebx, eax
0x180019bf5  test    eax, eax
0x180019bf7  js      short loc_180019C72
0x180019bf9  mov     rcx, [rbp+210h+var_290]
0x180019bfd  mov     rdx, rdi
0x180019c00  mov     rax, [rcx]
0x180019c03  mov     rax, [rax+18h]
0x180019c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c0c  mov     ebx, eax
0x180019c0e  jmp     short loc_180019C72
0x180019c10  xor     r14d, r14d
0x180019c13  cmp     r14d, eax
0x180019c16  jnb     loc_180019B91
0x180019c1c  mov     rax, [r15]
0x180019c1f  lea     r9, [rsp+310h+var_298]
0x180019c24  lea     r8, [rsp+310h+var_2A0]
0x180019c29  mov     edx, r14d
0x180019c2c  mov     rcx, r15
0x180019c2f  mov     rax, [rax+20h]
0x180019c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c38  mov     ebx, eax
0x180019c3a  test    eax, eax
0x180019c3c  js      short loc_180019C72
0x180019c3e  mov     rax, [rsi]
0x180019c41  mov     rcx, rsi
0x180019c44  mov     r8, [rsp+310h+var_2A0]
0x180019c49  mov     rdx, [rsp+310h+var_2C8]
0x180019c4e  mov     rax, [rax+68h]
0x180019c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c57  mov     ebx, eax
0x180019c59  test    eax, eax
0x180019c5b  js      short loc_180019C72
0x180019c5d  mov     eax, [rsp+310h+var_2D0]
0x180019c61  inc     r14d
0x180019c64  jmp     short loc_180019C13
0x180019c66  mov     ebx, 80070008h
0x180019c6b  jmp     short loc_180019C72
0x180019c6d  mov     ebx, 80070057h
0x180019c72  mov     rcx, [rsp+310h+var_2B0]
0x180019c77  xor     esi, esi
0x180019c79  test    rcx, rcx
0x180019c7c  jz      short loc_180019C8F
0x180019c7e  mov     rax, [rcx]
0x180019c81  mov     rax, [rax+10h]
0x180019c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c8a  mov     [rsp+310h+var_2B0], rsi
0x180019c8f  mov     rcx, [rsp+310h+var_2A8]
0x180019c94  test    rcx, rcx
0x180019c97  jz      short loc_180019CAA
0x180019c99  mov     rax, [rcx]
0x180019c9c  mov     rax, [rax+10h]
0x180019ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ca5  mov     [rsp+310h+var_2A8], rsi
0x180019caa  mov     rcx, [rsp+310h+var_2C8]
0x180019caf  test    rcx, rcx
0x180019cb2  jz      short loc_180019CC5
0x180019cb4  mov     rax, [rcx]
0x180019cb7  mov     rax, [rax+10h]
0x180019cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc0  mov     [rsp+310h+var_2C8], rsi
0x180019cc5  mov     rcx, [rsp+310h+var_2C0]
0x180019cca  test    rcx, rcx
0x180019ccd  jz      short loc_180019CE0
0x180019ccf  mov     rax, [rcx]
0x180019cd2  mov     rax, [rax+10h]
0x180019cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cdb  mov     [rsp+310h+var_2C0], rsi
0x180019ce0  test    rdi, rdi
0x180019ce3  jz      short loc_180019CF4
0x180019ce5  mov     rax, [rdi]
0x180019ce8  mov     rcx, rdi
0x180019ceb  mov     rax, [rax+10h]
0x180019cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cf4  lea     rcx, [rbp+210h+var_278]; this
0x180019cf8  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180019cfd  mov     eax, ebx
0x180019cff  mov     rcx, [rbp+210h+var_40]
0x180019d06  xor     rcx, rsp; StackCookie
0x180019d09  call    __security_check_cookie
0x180019d0e  mov     rbx, [rsp+310h+arg_0]
0x180019d16  add     rsp, 2E0h
0x180019d1d  pop     r15
0x180019d1f  pop     r14
0x180019d21  pop     r13
0x180019d23  pop     r12
0x180019d25  pop     rdi
0x180019d26  pop     rsi
0x180019d27  pop     rbp
0x180019d28  retn
```
