# APPPOOL_OBJECT_EXTENSION::AddAppPool(IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180016e74`
- end: `0x1800172e6`
- name: `?AddAppPool@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `1138`
- prototype: `__int64 __fastcall(APPPOOL_OBJECT_EXTENSION *this, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017f90`

## callees

- `0x180001044`
- `0x180016e28`
- `0x180016e74`
- `0x1800172ec`
- `0x180018540`
- `0x18002a6cc`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall APPPOOL_OBJECT_EXTENSION::AddAppPool(
        APPPOOL_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        struct ICommandObjectList *a4,
        struct IXMLDOMDocument *a5)
{
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  APPPOOL_OBJECT *v11; // rax
  APPPOOL_OBJECT *v12; // rdi
  int v13; // eax
  __int64 v14; // rax
  APP_OBJECT_UTILS *v15; // rcx
  unsigned int v16; // r8d
  struct INativeConfigurationElement *v18; // [rsp+40h] [rbp-41h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-39h] BYREF
  __int64 v20; // [rsp+50h] [rbp-31h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+58h] [rbp-29h] BYREF
  __int64 v22; // [rsp+60h] [rbp-21h] BYREF
  __int64 v23; // [rsp+68h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp-9h] BYREF
  unsigned __int16 *v26[2]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v27; // [rsp+90h] [rbp+Fh]

  v21 = 0;
  v18 = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v22 = 0;
  v27 = 0;
  v25 = 0;
  v19 = 0;
  *(_OWORD *)v26 = 0;
  if ( a2 && a3 && a4 )
  {
    v8 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)a3 + 40LL))(
           a3,
           L"name",
           &v19);
    v9 = v8;
    if ( v8 == -2147023483 )
    {
      if ( (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)a3 + 40LL))(
             a3,
             L"APPPOOL.NAME",
             &v19) < 0 )
      {
        v10 = *(_QWORD *)a2;
        v9 = -2147024809;
        v26[0] = L"name";
        v26[1] = 0;
        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(v10 + 144))(
          a2,
          2147942487LL,
          3221226486LL,
          v26,
          0);
        goto LABEL_32;
      }
    }
    else if ( v8 < 0 )
    {
      goto LABEL_32;
    }
    v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
           a2,
           L"MACHINE/WEBROOT/APPHOST",
           &v23);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *, _QWORD))(*(_QWORD *)v23 + 24LL))(
             v23,
             L"system.applicationHost/applicationPools",
             L"MACHINE/WEBROOT/APPHOST",
             &v21,
             &v24,
             0);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v21 + 40LL))(
               v21,
               &v20);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v20 + 48LL))(
                 v20,
                 L"add",
                 &v18);
          if ( v9 >= 0 )
          {
            v11 = (APPPOOL_OBJECT *)operator new(0xD8u);
            if ( v11 && (v12 = APPPOOL_OBJECT::APPPOOL_OBJECT(v11, v18, v21)) != 0 )
            {
              v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                     a2,
                     v18,
                     L"name",
                     v19);
              if ( v9 >= 0 )
              {
                v9 = APPPOOL_OBJECT::Reset(v12);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, APPPOOL_OBJECT *, struct ICommandParameterList *, _QWORD, struct IXMLDOMDocument *, int))(*(_QWORD *)a2 + 168LL))(
                         a2,
                         v12,
                         a3,
                         0,
                         a5,
                         1);
                  if ( v9 >= 0 )
                  {
                    v13 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v20 + 56LL))(
                            v20,
                            v18,
                            0xFFFFFFFFLL,
                            &v22);
                    v9 = v13;
                    if ( v13 >= 0 )
                    {
                      v9 = APPPOOL_OBJECT::Create(v12, L"MACHINE/WEBROOT/APPHOST", 4);
                      if ( v9 >= 0 )
                      {
                        v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                               a2,
                               L"MACHINE/WEBROOT/APPHOST",
                               0);
                        if ( v9 >= 0 )
                        {
                          v26[0] = L"APPPOOL";
                          v26[1] = v19;
                          v9 = APP_OBJECT_UTILS::AddStatusObject(v15, a4, v16, (const unsigned __int16 **const)v26);
                        }
                      }
                    }
                    else if ( v13 == -2147024713 )
                    {
                      v26[0] = v19;
                      v14 = *(_QWORD *)a2;
                      v26[1] = 0;
                      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(v14 + 144))(
                        a2,
                        2147942583LL,
                        3221226483LL,
                        v26,
                        0);
                    }
                    else if ( v22 )
                    {
                      (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 24LL))(v22, &v25);
                      if ( v25 )
                      {
                        v26[1] = v25;
                        v26[0] = L"APPPOOL";
                        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
                          a2,
                          (unsigned int)v9,
                          3221226480LL,
                          v26,
                          0);
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                      v22 = 0;
                    }
                  }
                }
              }
              (*(void (__fastcall **)(APPPOOL_OBJECT *))(*(_QWORD *)v12 + 16LL))(v12);
            }
            else
            {
              v9 = -2147024888;
            }
          }
        }
      }
      else if ( v24 )
      {
        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
          a2,
          (unsigned int)v9,
          &Str,
          v24,
          0);
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_32:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016e74  mov     [rsp-8+arg_0], rbx
0x180016e79  push    rbp
0x180016e7a  push    rsi
0x180016e7b  push    rdi
0x180016e7c  push    r12
0x180016e7e  push    r13
0x180016e80  push    r14
0x180016e82  push    r15
0x180016e84  lea     rbp, [rsp-1Fh]
0x180016e89  sub     rsp, 0A0h
0x180016e90  mov     rax, cs:__security_cookie
0x180016e97  xor     rax, rsp
0x180016e9a  mov     [rbp+4Fh+var_38], rax
0x180016e9e  mov     r12, [rbp+4Fh+arg_20]
0x180016ea2  xor     r13d, r13d
0x180016ea5  xor     eax, eax
0x180016ea7  mov     [rbp+4Fh+var_78], r13
0x180016eab  mov     [rbp+4Fh+var_90], r13
0x180016eaf  xorps   xmm0, xmm0
0x180016eb2  mov     [rbp+4Fh+var_80], r13
0x180016eb6  mov     r15, r9
0x180016eb9  mov     [rbp+4Fh+var_68], r13
0x180016ebd  mov     r14, r8
0x180016ec0  mov     [rbp+4Fh+var_60], r13
0x180016ec4  mov     rsi, rdx
0x180016ec7  mov     [rbp+4Fh+var_70], r13
0x180016ecb  mov     [rbp+4Fh+var_40], rax
0x180016ecf  mov     [rbp+4Fh+var_58], r13
0x180016ed3  mov     [rbp+4Fh+var_88], r13
0x180016ed7  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x180016edb  test    rdx, rdx
0x180016ede  jz      loc_180017226
0x180016ee4  test    r8, r8
0x180016ee7  jz      loc_180017226
0x180016eed  test    r9, r9
0x180016ef0  jz      loc_180017226
0x180016ef6  mov     rax, [r8]
0x180016ef9  lea     rdi, aName_0; "name"
0x180016f00  lea     r8, [rbp+4Fh+var_88]
0x180016f04  mov     rdx, rdi
0x180016f07  mov     rcx, r14
0x180016f0a  mov     rax, [rax+28h]
0x180016f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f13  mov     ebx, eax
0x180016f15  cmp     eax, 80070585h
0x180016f1a  jnz     short loc_180016F6F
0x180016f1c  mov     rax, [r14]
0x180016f1f  lea     r8, [rbp+4Fh+var_88]
0x180016f23  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x180016f2a  mov     rcx, r14
0x180016f2d  mov     rax, [rax+28h]
0x180016f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f36  test    eax, eax
0x180016f38  jns     short loc_180016F77
0x180016f3a  mov     rax, [rsi]
0x180016f3d  lea     r9, [rbp+4Fh+var_50]
0x180016f41  mov     ebx, 80070057h
0x180016f46  mov     [rbp+4Fh+var_50], rdi
0x180016f4a  mov     r8d, 0C00003F6h
0x180016f50  mov     [rbp+4Fh+var_50+8], r13
0x180016f54  mov     edx, ebx
0x180016f56  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180016f5b  mov     rax, [rax+90h]
0x180016f62  mov     rcx, rsi
0x180016f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f6a  jmp     loc_18001722B
0x180016f6f  test    eax, eax
0x180016f71  js      loc_18001722B
0x180016f77  mov     rax, [rsi]
0x180016f7a  lea     r8, [rbp+4Fh+var_68]
0x180016f7e  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180016f85  mov     rcx, rsi
0x180016f88  mov     rax, [rax+50h]
0x180016f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f91  mov     ebx, eax
0x180016f93  test    eax, eax
0x180016f95  js      loc_18001722B
0x180016f9b  mov     rcx, [rbp+4Fh+var_68]
0x180016f9f  lea     rdx, [rbp+4Fh+var_60]
0x180016fa3  mov     [rsp+0D0h+var_A8], r13
0x180016fa8  lea     r9, [rbp+4Fh+var_78]
0x180016fac  mov     [rsp+0D0h+var_B0], rdx
0x180016fb1  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180016fb8  lea     rdx, aSystemApplicat_3; "system.applicationHost/applicationPools"
0x180016fbf  mov     rax, [rcx]
0x180016fc2  mov     rax, [rax+18h]
0x180016fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fcb  mov     ebx, eax
0x180016fcd  test    eax, eax
0x180016fcf  jns     short loc_180017003
0x180016fd1  mov     rcx, [rbp+4Fh+var_60]
0x180016fd5  test    rcx, rcx
0x180016fd8  jz      loc_18001722B
0x180016fde  mov     rax, [rsi]
0x180016fe1  lea     r8, Str
0x180016fe8  mov     r9, rcx
0x180016feb  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180016ff0  mov     edx, ebx
0x180016ff2  mov     rcx, rsi
0x180016ff5  mov     rax, [rax+70h]
0x180016ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffe  jmp     loc_18001722B
0x180017003  mov     rcx, [rbp+4Fh+var_78]
0x180017007  lea     rdx, [rbp+4Fh+var_80]
0x18001700b  mov     rax, [rcx]
0x18001700e  mov     rax, [rax+28h]
0x180017012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017017  mov     ebx, eax
0x180017019  test    eax, eax
0x18001701b  js      loc_18001722B
0x180017021  mov     rcx, [rbp+4Fh+var_80]
0x180017025  lea     r8, [rbp+4Fh+var_90]
0x180017029  lea     rdx, aAdd; "add"
0x180017030  mov     rax, [rcx]
0x180017033  mov     rax, [rax+30h]
0x180017037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001703c  mov     ebx, eax
0x18001703e  test    eax, eax
0x180017040  js      loc_18001722B
0x180017046  mov     ecx, 0D8h; Size
0x18001704b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017050  test    rax, rax
0x180017053  jz      loc_18001721F
0x180017059  mov     r8, [rbp+4Fh+var_78]; struct INativeConfigurationElement *
0x18001705d  mov     rcx, rax; this
0x180017060  mov     rdx, [rbp+4Fh+var_90]; struct INativeConfigurationElement *
0x180017064  call    ??0APPPOOL_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; APPPOOL_OBJECT::APPPOOL_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180017069  mov     rdi, rax
0x18001706c  test    rax, rax
0x18001706f  jz      loc_18001721F
0x180017075  mov     rax, [rsi]
0x180017078  lea     r8, aName_0; "name"
0x18001707f  mov     r9, [rbp+4Fh+var_88]
0x180017083  mov     rcx, rsi
0x180017086  mov     rdx, [rbp+4Fh+var_90]
0x18001708a  mov     rax, [rax+60h]
0x18001708e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017093  mov     ebx, eax
0x180017095  test    eax, eax
0x180017097  js      loc_18001720E
0x18001709d  mov     rcx, rdi; this
0x1800170a0  call    ?Reset@APPPOOL_OBJECT@@QEAAJXZ; APPPOOL_OBJECT::Reset(void)
0x1800170a5  mov     ebx, eax
0x1800170a7  test    eax, eax
0x1800170a9  js      loc_18001720E
0x1800170af  mov     rax, [rsi]
0x1800170b2  xor     r9d, r9d
0x1800170b5  mov     dword ptr [rsp+0D0h+var_A8], 1
0x1800170bd  mov     r8, r14
0x1800170c0  mov     rdx, rdi
0x1800170c3  mov     [rsp+0D0h+var_B0], r12
0x1800170c8  mov     rcx, rsi
0x1800170cb  mov     rax, [rax+0A8h]
0x1800170d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d7  mov     ebx, eax
0x1800170d9  test    eax, eax
0x1800170db  js      loc_18001720E
0x1800170e1  mov     rcx, [rbp+4Fh+var_80]
0x1800170e5  lea     r9, [rbp+4Fh+var_70]
0x1800170e9  mov     rdx, [rbp+4Fh+var_90]
0x1800170ed  or      r8d, 0FFFFFFFFh
0x1800170f1  mov     rax, [rcx]
0x1800170f4  mov     rax, [rax+38h]
0x1800170f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170fd  mov     ebx, eax
0x1800170ff  test    eax, eax
0x180017101  jns     loc_1800171B0
0x180017107  mov     edx, 800700B7h
0x18001710c  cmp     eax, edx
0x18001710e  jnz     short loc_180017142
0x180017110  mov     rax, [rbp+4Fh+var_88]
0x180017114  lea     r9, [rbp+4Fh+var_50]
0x180017118  mov     [rbp+4Fh+var_50], rax
0x18001711c  mov     r8d, 0C00003F3h
0x180017122  mov     rax, [rsi]
0x180017125  mov     rcx, rsi
0x180017128  mov     [rbp+4Fh+var_50+8], r13
0x18001712c  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180017131  mov     rax, [rax+90h]
0x180017138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001713d  jmp     loc_18001720E
0x180017142  mov     rcx, [rbp+4Fh+var_70]
0x180017146  test    rcx, rcx
0x180017149  jz      loc_18001720E
0x18001714f  mov     rax, [rcx]
0x180017152  lea     rdx, [rbp+4Fh+var_58]
0x180017156  mov     rax, [rax+18h]
0x18001715a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715f  mov     rcx, [rbp+4Fh+var_58]
0x180017163  test    rcx, rcx
0x180017166  jz      short loc_18001719A
0x180017168  lea     rax, aApppool; "APPPOOL"
0x18001716f  mov     [rbp+4Fh+var_50+8], rcx
0x180017173  mov     [rbp+4Fh+var_50], rax
0x180017177  lea     r9, [rbp+4Fh+var_50]
0x18001717b  mov     rax, [rsi]
0x18001717e  mov     r8d, 0C00003F0h
0x180017184  mov     edx, ebx
0x180017186  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x18001718b  mov     rcx, rsi
0x18001718e  mov     rax, [rax+90h]
0x180017195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719a  mov     rcx, [rbp+4Fh+var_70]
0x18001719e  mov     rax, [rcx]
0x1800171a1  mov     rax, [rax+10h]
0x1800171a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171aa  mov     [rbp+4Fh+var_70], r13
0x1800171ae  jmp     short loc_18001720E
0x1800171b0  mov     r8d, 4
0x1800171b6  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800171bd  mov     rcx, rdi
0x1800171c0  call    ?Create@APPPOOL_OBJECT@@QEAAJPEBGW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z; APPPOOL_OBJECT::Create(ushort const *,__MIDL___MIDL_itf_rscaps_0000_0003_0001)
0x1800171c5  mov     ebx, eax
0x1800171c7  test    eax, eax
0x1800171c9  js      short loc_18001720E
0x1800171cb  mov     rax, [rsi]
0x1800171ce  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800171d5  xor     r8d, r8d
0x1800171d8  mov     rcx, rsi
0x1800171db  mov     rax, [rax+0D0h]
0x1800171e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e7  mov     ebx, eax
0x1800171e9  test    eax, eax
0x1800171eb  js      short loc_18001720E
0x1800171ed  lea     rax, aApppool; "APPPOOL"
0x1800171f4  mov     rdx, r15; struct ICommandObjectList *
0x1800171f7  mov     [rbp+4Fh+var_50], rax
0x1800171fb  lea     r9, [rbp+4Fh+var_50]; unsigned __int16 **
0x1800171ff  mov     rax, [rbp+4Fh+var_88]
0x180017203  mov     [rbp+4Fh+var_50+8], rax
0x180017207  call    ?AddStatusObject@APP_OBJECT_UTILS@@QEAAJPEAVICommandObjectList@@KQEAPEBG@Z; APP_OBJECT_UTILS::AddStatusObject(ICommandObjectList *,ulong,ushort const * * const)
0x18001720c  mov     ebx, eax
0x18001720e  mov     rax, [rdi]
0x180017211  mov     rcx, rdi
0x180017214  mov     rax, [rax+10h]
0x180017218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721d  jmp     short loc_18001722B
0x18001721f  mov     ebx, 80070008h
0x180017224  jmp     short loc_18001722B
0x180017226  mov     ebx, 80070057h
0x18001722b  mov     rcx, [rbp+4Fh+var_90]
0x18001722f  test    rcx, rcx
0x180017232  jz      short loc_180017244
0x180017234  mov     rax, [rcx]
0x180017237  mov     rax, [rax+10h]
0x18001723b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017240  mov     [rbp+4Fh+var_90], r13
0x180017244  mov     rcx, [rbp+4Fh+var_80]
0x180017248  test    rcx, rcx
0x18001724b  jz      short loc_18001725D
0x18001724d  mov     rax, [rcx]
0x180017250  mov     rax, [rax+10h]
0x180017254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017259  mov     [rbp+4Fh+var_80], r13
0x18001725d  mov     rcx, [rbp+4Fh+var_78]
0x180017261  test    rcx, rcx
0x180017264  jz      short loc_180017276
0x180017266  mov     rax, [rcx]
0x180017269  mov     rax, [rax+10h]
0x18001726d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017272  mov     [rbp+4Fh+var_78], r13
0x180017276  mov     rcx, [rbp+4Fh+var_68]
0x18001727a  test    rcx, rcx
0x18001727d  jz      short loc_18001728F
0x18001727f  mov     rax, [rcx]
0x180017282  mov     rax, [rax+10h]
0x180017286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001728b  mov     [rbp+4Fh+var_68], r13
0x18001728f  mov     rcx, [rbp+4Fh+var_60]
0x180017293  test    rcx, rcx
0x180017296  jz      short loc_1800172A8
0x180017298  mov     rax, [rcx]
0x18001729b  mov     rax, [rax+10h]
0x18001729f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a4  mov     [rbp+4Fh+var_60], r13
0x1800172a8  mov     rcx, [rbp+4Fh+var_70]
0x1800172ac  test    rcx, rcx
0x1800172af  jz      short loc_1800172BD
0x1800172b1  mov     rax, [rcx]
0x1800172b4  mov     rax, [rax+10h]
0x1800172b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172bd  mov     eax, ebx
0x1800172bf  mov     rcx, [rbp+4Fh+var_38]
0x1800172c3  xor     rcx, rsp; StackCookie
0x1800172c6  call    __security_check_cookie
0x1800172cb  mov     rbx, [rsp+0D0h+arg_0]
0x1800172d3  add     rsp, 0A0h
0x1800172da  pop     r15
0x1800172dc  pop     r14
0x1800172de  pop     r13
0x1800172e0  pop     r12
0x1800172e2  pop     rdi
0x1800172e3  pop     rsi
0x1800172e4  pop     rbp
0x1800172e5  retn
```
