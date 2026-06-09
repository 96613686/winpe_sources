# COMMAND_PROCESSOR::SetObject(ICommandObject *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)

- ea: `0x18000cd60`
- end: `0x18000d20b`
- name: `?SetObject@COMMAND_PROCESSOR@@UEAAJPEAVICommandObject@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z`
- size: `1195`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x18000557c`
- `0x180006b6c`
- `0x18000774c`
- `0x180009aac`
- `0x18000cd60`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::SetObject(
        COMMAND_PROCESSOR *this,
        struct ICommandObject *a2,
        struct ICommandParameterList *a3,
        struct ICommandObjectList *a4,
        struct IXMLDOMDocument *a5,
        int a6)
{
  int v9; // ebx
  BOOL v10; // esi
  unsigned int i; // r15d
  wchar_t *v12; // rax
  unsigned int v13; // edx
  int SetConfigPropertyInternal; // eax
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  const unsigned __int16 **v18; // rdi
  struct ICommandObjectList *v19; // r13
  STATUS_OBJECT *v20; // rax
  va_list v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v24; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMNode *v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  va_list Arguments[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  va_list v30; // [rsp+88h] [rbp-78h] BYREF
  va_list v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  struct ICommandObjectList *v33; // [rsp+A0h] [rbp-60h]
  _BYTE v34[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 *v35; // [rsp+C8h] [rbp-38h]
  int v36; // [rsp+D0h] [rbp-30h]
  __int16 v37; // [rsp+D4h] [rbp-2Ch]
  int v38; // [rsp+D8h] [rbp-28h]
  __int16 v39; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v40[510]; // [rsp+E2h] [rbp-1Eh] BYREF

  v23 = 0;
  v22 = 0;
  v28 = 0;
  v29 = 0;
  v33 = a4;
  memset_0(v40, 0, sizeof(v40));
  v36 = 512;
  v35 = &v39;
  v37 = 256;
  v38 = 0;
  v39 = 0;
  v24 = 0;
  v30 = 0;
  v31 = 0;
  v26 = 0;
  v32 = 0;
  v25 = 0;
  *(_OWORD *)Arguments = 0;
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    goto LABEL_49;
  }
  v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, struct INativeConfigurationElement **))(*(_QWORD *)a2 + 48LL))(
         a2,
         &v24);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)a3 + 24LL))(a3, &v23);
    if ( v9 >= 0 )
    {
      v10 = 0;
      if ( a5 )
      {
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMNode **))a5->lpVtbl->get_firstChild)(
               a5,
               &v25);
        if ( v9 < 0 )
          goto LABEL_49;
        v9 = COMMAND_PROCESSOR::FillConfigElementFromXML((COMMAND_PROCESSOR *)((char *)this - 8), v24, v25);
        if ( v9 < 0 )
          goto LABEL_49;
        v10 = v9 != 1;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= v23 )
        {
          if ( !a6 && !v10 )
          {
            v9 = -2147024809;
            v16 = 3221226525LL;
            v17 = 2147942487LL;
            goto LABEL_30;
          }
          v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, &v29);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(COMMAND_PROCESSOR *, __int64, _QWORD))(*(_QWORD *)this + 208LL))(
                   this,
                   v29,
                   0);
            if ( v9 >= 0 )
            {
              v18 = 0;
              v19 = v33;
              if ( v33 && v10 )
              {
                v20 = (STATUS_OBJECT *)operator new(0x110u);
                if ( v20 && (v18 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v20)) != 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a2 + 24LL))(a2, &v30);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a2 + 32LL))(
                           a2,
                           &v31);
                    if ( v9 >= 0 )
                    {
                      Arguments[0] = v30;
                      Arguments[1] = v31;
                      v9 = STATUS_OBJECT::Create(v18, 0x3EEu, Arguments);
                      if ( v9 >= 0 )
                      {
                        v9 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)v19 + 24LL))(
                               v19,
                               v18);
                        if ( v9 >= 0 )
                          goto LABEL_46;
                      }
                    }
                  }
LABEL_47:
                  (*((void (__fastcall **)(const unsigned __int16 **))*v18 + 2))(v18);
                }
                else
                {
                  v9 = -2147024888;
                }
              }
              else
              {
LABEL_46:
                v9 = 0;
                if ( v18 )
                  goto LABEL_47;
              }
            }
          }
          break;
        }
        v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, va_list *, unsigned __int16 **))(*(_QWORD *)a3 + 32LL))(
               a3,
               i,
               &v22,
               &v28);
        if ( v9 < 0 )
          break;
        v9 = STRU::Copy((STRU *)v34, (const unsigned __int8 *)v28);
        if ( v9 < 0 )
          break;
        v12 = (wchar_t *)v22;
        switch ( *(_WORD *)v22 )
        {
          case '-':
            v12 = (wchar_t *)(v22 + 2);
            v13 = 4;
            v22 += 2;
            break;
          case '+':
            v12 = (wchar_t *)(v22 + 2);
            v13 = 2;
            v22 += 2;
            break;
          case '~':
            v12 = (wchar_t *)(v22 + 2);
            v13 = 3;
            v22 += 2;
            break;
          default:
            v13 = 1;
            break;
        }
        SetConfigPropertyInternal = COMMAND_PROCESSOR::GetSetConfigPropertyInternal(
                                      (COMMAND_PROCESSOR *)((char *)this - 8),
                                      v13,
                                      v24,
                                      (unsigned __int16 *)&Str,
                                      v12,
                                      (STRU *)v34,
                                      0);
        v9 = SetConfigPropertyInternal;
        if ( SetConfigPropertyInternal == -2147023483 )
        {
          v15 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list, __int64 *))(*(_QWORD *)a2 + 80LL))(
                  a2,
                  v22,
                  &v32);
          v9 = v15;
          if ( v15 >= 0 )
            continue;
          if ( v15 != -2147023483
            || (*(int (__fastcall **)(char *, __int64 *))(*((_QWORD *)this - 1) + 56LL))((char *)this - 8, &v26) >= 0 )
          {
            break;
          }
          if ( ((*(__int64 (__fastcall **)(COMMAND_PROCESSOR *))(*(_QWORD *)this + 32LL))(this) & 2) == 0
            || (SetConfigPropertyInternal = (*(__int64 (__fastcall **)(struct ICommandParameterList *, va_list, _QWORD, _QWORD))(*(_QWORD *)a3 + 96LL))(
                                              a3,
                                              v22,
                                              0,
                                              0),
                v9 = SetConfigPropertyInternal,
                SetConfigPropertyInternal == -2147023728) )
          {
            v9 = -2147023483;
            Arguments[0] = v22;
            v16 = 3221226523LL;
            v17 = 2147943813LL;
LABEL_30:
            (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)this + 144LL))(
              this,
              v17,
              v16,
              Arguments,
              0);
            break;
          }
        }
        if ( SetConfigPropertyInternal < 0 )
          break;
        v10 = 1;
      }
    }
  }
LABEL_49:
  if ( v24 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v25 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v34);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000cd60  push    rbp
0x18000cd62  push    rbx
0x18000cd63  push    rsi
0x18000cd64  push    rdi
0x18000cd65  push    r12
0x18000cd67  push    r13
0x18000cd69  push    r14
0x18000cd6b  push    r15
0x18000cd6d  lea     rbp, [rsp-1F8h]
0x18000cd75  sub     rsp, 2F8h
0x18000cd7c  mov     rax, cs:__security_cookie
0x18000cd83  xor     rax, rsp
0x18000cd86  mov     [rbp+230h+var_50], rax
0x18000cd8d  mov     r15, [rbp+230h+arg_20]
0x18000cd94  xor     r13d, r13d
0x18000cd97  mov     r12, r8
0x18000cd9a  mov     [rsp+330h+var_2E8], r13d
0x18000cd9f  mov     r14, rdx
0x18000cda2  mov     [rsp+330h+var_2F0], r13
0x18000cda7  mov     rdi, rcx
0x18000cdaa  mov     [rsp+330h+var_2B8], r13
0x18000cdaf  xor     edx, edx; Val
0x18000cdb1  mov     [rbp+230h+var_2B0], r13
0x18000cdb5  mov     r8d, 1FEh; Size
0x18000cdbb  mov     [rbp+230h+var_290], r9
0x18000cdbf  lea     rcx, [rbp+230h+var_24E]; void *
0x18000cdc3  call    memset_0
0x18000cdc8  mov     [rbp+230h+var_260], 200h
0x18000cdcf  lea     rax, [rbp+230h+var_250]
0x18000cdd3  mov     [rbp+230h+var_268], rax
0x18000cdd7  xorps   xmm0, xmm0
0x18000cdda  mov     [rbp+230h+var_25C], 100h
0x18000cde0  mov     [rbp+230h+var_258], r13d
0x18000cde4  mov     [rbp+230h+var_250], r13w
0x18000cde9  mov     [rsp+330h+var_2E0], r13
0x18000cdee  mov     [rbp+230h+var_2A8], r13
0x18000cdf2  mov     [rbp+230h+var_2A0], r13
0x18000cdf6  mov     [rsp+330h+var_2D0], r13
0x18000cdfb  mov     [rbp+230h+var_298], r13
0x18000cdff  mov     [rsp+330h+var_2D8], r13
0x18000ce04  movups  xmmword ptr [rsp+330h+Arguments], xmm0
0x18000ce09  test    r14, r14
0x18000ce0c  jz      loc_18000D185
0x18000ce12  test    r12, r12
0x18000ce15  jz      loc_18000D185
0x18000ce1b  mov     rax, [r14]
0x18000ce1e  lea     rdx, [rsp+330h+var_2E0]
0x18000ce23  mov     rcx, r14
0x18000ce26  mov     rax, [rax+30h]
0x18000ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2f  mov     ebx, eax
0x18000ce31  test    eax, eax
0x18000ce33  js      loc_18000D18A
0x18000ce39  mov     rax, [r12]
0x18000ce3d  lea     rdx, [rsp+330h+var_2E8]
0x18000ce42  mov     rcx, r12
0x18000ce45  mov     rax, [rax+18h]
0x18000ce49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce4e  mov     ebx, eax
0x18000ce50  test    eax, eax
0x18000ce52  js      loc_18000D18A
0x18000ce58  mov     esi, r13d
0x18000ce5b  test    r15, r15
0x18000ce5e  jz      short loc_18000CEA4
0x18000ce60  mov     rax, [r15]
0x18000ce63  lea     rdx, [rsp+330h+var_2D8]
0x18000ce68  mov     rcx, r15
0x18000ce6b  mov     rax, [rax+68h]
0x18000ce6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce74  mov     ebx, eax
0x18000ce76  test    eax, eax
0x18000ce78  js      loc_18000D18A
0x18000ce7e  mov     r8, [rsp+330h+var_2D8]; struct IXMLDOMNode *
0x18000ce83  lea     rcx, [rdi-8]; this
0x18000ce87  mov     rdx, [rsp+330h+var_2E0]; struct INativeConfigurationElement *
0x18000ce8c  call    ?FillConfigElementFromXML@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEAUIXMLDOMNode@@@Z; COMMAND_PROCESSOR::FillConfigElementFromXML(INativeConfigurationElement *,IXMLDOMNode *)
0x18000ce91  mov     ebx, eax
0x18000ce93  test    eax, eax
0x18000ce95  js      loc_18000D18A
0x18000ce9b  lea     eax, [r13+1]
0x18000ce9f  cmp     ebx, eax
0x18000cea1  cmovnz  esi, eax
0x18000cea4  mov     r15d, r13d
0x18000cea7  cmp     r15d, [rsp+330h+var_2E8]
0x18000ceac  jnb     loc_18000D051
0x18000ceb2  mov     rax, [r12]
0x18000ceb6  lea     r9, [rsp+330h+var_2B8]
0x18000cebb  lea     r8, [rsp+330h+var_2F0]
0x18000cec0  mov     edx, r15d
0x18000cec3  mov     rcx, r12
0x18000cec6  mov     rax, [rax+20h]
0x18000ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cecf  mov     ebx, eax
0x18000ced1  test    eax, eax
0x18000ced3  js      loc_18000D18A
0x18000ced9  mov     rdx, [rsp+330h+var_2B8]; unsigned __int16 *
0x18000cede  lea     rcx, [rbp+230h+var_288]; this
0x18000cee2  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000cee7  mov     ebx, eax
0x18000cee9  test    eax, eax
0x18000ceeb  js      loc_18000D18A
0x18000cef1  mov     rax, [rsp+330h+var_2F0]
0x18000cef6  cmp     word ptr [rax], 2Dh ; '-'
0x18000cefa  jnz     short loc_18000CF0C
0x18000cefc  add     rax, 2
0x18000cf00  mov     edx, 4
0x18000cf05  mov     [rsp+330h+var_2F0], rax
0x18000cf0a  jmp     short loc_18000CF3D
0x18000cf0c  cmp     word ptr [rax], 2Bh ; '+'
0x18000cf10  jnz     short loc_18000CF22
0x18000cf12  add     rax, 2
0x18000cf16  mov     edx, 2
0x18000cf1b  mov     [rsp+330h+var_2F0], rax
0x18000cf20  jmp     short loc_18000CF3D
0x18000cf22  cmp     word ptr [rax], 7Eh ; '~'
0x18000cf26  jnz     short loc_18000CF38
0x18000cf28  add     rax, 2
0x18000cf2c  mov     edx, 3
0x18000cf31  mov     [rsp+330h+var_2F0], rax
0x18000cf36  jmp     short loc_18000CF3D
0x18000cf38  mov     edx, 1
0x18000cf3d  mov     r8, [rsp+330h+var_2E0]
0x18000cf42  lea     rcx, [rbp+230h+var_288]
0x18000cf46  mov     [rsp+330h+var_300], 0
0x18000cf4f  lea     r13, [rdi-8]
0x18000cf53  mov     [rsp+330h+var_308], rcx
0x18000cf58  lea     r9, Str
0x18000cf5f  mov     rcx, r13
0x18000cf62  mov     [rsp+330h+var_310], rax
0x18000cf67  call    ?GetSetConfigPropertyInternal@COMMAND_PROCESSOR@@AEAAJW4CONFIG_OPERATION_TYPE@@PEAVINativeConfigurationElement@@PEBG2PEAVSTRU@@PEAH@Z; COMMAND_PROCESSOR::GetSetConfigPropertyInternal(CONFIG_OPERATION_TYPE,INativeConfigurationElement *,ushort const *,ushort const *,STRU *,int *)
0x18000cf6c  mov     ebx, eax
0x18000cf6e  cmp     eax, 80070585h
0x18000cf73  jnz     loc_18000CFFB
0x18000cf79  mov     rax, [r14]
0x18000cf7c  lea     r8, [rbp+230h+var_298]
0x18000cf80  mov     rdx, [rsp+330h+var_2F0]
0x18000cf85  mov     rcx, r14
0x18000cf88  mov     rax, [rax+50h]
0x18000cf8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf91  mov     ebx, eax
0x18000cf93  test    eax, eax
0x18000cf95  jns     short loc_18000D00C
0x18000cf97  mov     esi, 80070585h
0x18000cf9c  cmp     eax, esi
0x18000cf9e  jnz     loc_18000D18A
0x18000cfa4  mov     rax, [r13+0]
0x18000cfa8  lea     rdx, [rsp+330h+var_2D0]
0x18000cfad  mov     rcx, r13
0x18000cfb0  mov     rax, [rax+38h]
0x18000cfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb9  xor     r13d, r13d
0x18000cfbc  test    eax, eax
0x18000cfbe  jns     loc_18000D18A
0x18000cfc4  mov     rax, [rdi]
0x18000cfc7  mov     rcx, rdi
0x18000cfca  mov     rax, [rax+20h]
0x18000cfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd3  test    al, 2
0x18000cfd5  jz      short loc_18000D01C
0x18000cfd7  mov     rax, [r12]
0x18000cfdb  xor     r9d, r9d
0x18000cfde  mov     rdx, [rsp+330h+var_2F0]
0x18000cfe3  xor     r8d, r8d
0x18000cfe6  mov     rcx, r12
0x18000cfe9  mov     rax, [rax+60h]
0x18000cfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cff2  mov     ebx, eax
0x18000cff4  cmp     eax, 80070490h
0x18000cff9  jz      short loc_18000D01C
0x18000cffb  test    eax, eax
0x18000cffd  js      loc_18000D18A
0x18000d003  mov     eax, 1
0x18000d008  mov     esi, eax
0x18000d00a  jmp     short loc_18000D011
0x18000d00c  mov     eax, 1
0x18000d011  add     r15d, eax
0x18000d014  xor     r13d, r13d
0x18000d017  jmp     loc_18000CEA7
0x18000d01c  mov     rax, [rsp+330h+var_2F0]
0x18000d021  mov     ebx, esi
0x18000d023  mov     [rsp+330h+Arguments], rax
0x18000d028  mov     r8d, 0C000041Bh
0x18000d02e  mov     edx, esi
0x18000d030  mov     rax, [rdi]
0x18000d033  lea     r9, [rsp+330h+Arguments]
0x18000d038  mov     rcx, rdi
0x18000d03b  mov     dword ptr [rsp+330h+var_310], r13d
0x18000d040  mov     rax, [rax+90h]
0x18000d047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d04c  jmp     loc_18000D18A
0x18000d051  cmp     [rbp+230h+arg_28], r13d
0x18000d058  jnz     short loc_18000D06D
0x18000d05a  test    esi, esi
0x18000d05c  jnz     short loc_18000D06D
0x18000d05e  mov     ebx, 80070057h
0x18000d063  mov     r8d, 0C000041Dh
0x18000d069  mov     edx, ebx
0x18000d06b  jmp     short loc_18000D030
0x18000d06d  mov     rax, [r14]
0x18000d070  lea     rdx, [rbp+230h+var_2B0]
0x18000d074  mov     rcx, r14
0x18000d077  mov     rax, [rax+28h]
0x18000d07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d080  mov     ebx, eax
0x18000d082  test    eax, eax
0x18000d084  js      loc_18000D18A
0x18000d08a  mov     rax, [rdi]
0x18000d08d  xor     r8d, r8d
0x18000d090  mov     rdx, [rbp+230h+var_2B0]
0x18000d094  mov     rcx, rdi
0x18000d097  mov     rax, [rax+0D0h]
0x18000d09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0a3  mov     ebx, eax
0x18000d0a5  test    eax, eax
0x18000d0a7  js      loc_18000D18A
0x18000d0ad  mov     rdi, r13
0x18000d0b0  mov     r13, [rbp+230h+var_290]
0x18000d0b4  test    r13, r13
0x18000d0b7  jz      loc_18000D169
0x18000d0bd  test    esi, esi
0x18000d0bf  jz      loc_18000D169
0x18000d0c5  mov     ecx, 110h; Size
0x18000d0ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d0cf  test    rax, rax
0x18000d0d2  jz      loc_18000D162
0x18000d0d8  mov     rcx, rax; this
0x18000d0db  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x18000d0e0  mov     rdi, rax
0x18000d0e3  test    rax, rax
0x18000d0e6  jz      short loc_18000D162
0x18000d0e8  mov     rax, [r14]
0x18000d0eb  lea     rdx, [rbp+230h+var_2A8]
0x18000d0ef  mov     rcx, r14
0x18000d0f2  mov     rax, [rax+18h]
0x18000d0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0fb  mov     ebx, eax
0x18000d0fd  test    eax, eax
0x18000d0ff  js      short loc_18000D174
0x18000d101  mov     rax, [r14]
0x18000d104  lea     rdx, [rbp+230h+var_2A0]
0x18000d108  mov     rcx, r14
0x18000d10b  mov     rax, [rax+20h]
0x18000d10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d114  mov     ebx, eax
0x18000d116  test    eax, eax
0x18000d118  js      short loc_18000D174
0x18000d11a  mov     rax, [rbp+230h+var_2A8]
0x18000d11e  lea     r8, [rsp+330h+Arguments]; Arguments
0x18000d123  mov     [rsp+330h+Arguments], rax
0x18000d128  mov     edx, 3EEh; dwMessageId
0x18000d12d  mov     rax, [rbp+230h+var_2A0]
0x18000d131  mov     rcx, rdi; this
0x18000d134  mov     [rsp+330h+Arguments+8], rax
0x18000d139  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x18000d13e  mov     ebx, eax
0x18000d140  test    eax, eax
0x18000d142  js      short loc_18000D174
0x18000d144  mov     rax, [r13+0]
0x18000d148  mov     rdx, rdi
0x18000d14b  mov     rcx, r13
0x18000d14e  mov     rax, [rax+18h]
0x18000d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d157  xor     r13d, r13d
0x18000d15a  mov     ebx, eax
0x18000d15c  test    eax, eax
0x18000d15e  js      short loc_18000D174
0x18000d160  jmp     short loc_18000D16C
0x18000d162  mov     ebx, 80070008h
0x18000d167  jmp     short loc_18000D18A
0x18000d169  xor     r13d, r13d
0x18000d16c  mov     ebx, r13d
0x18000d16f  test    rdi, rdi
0x18000d172  jz      short loc_18000D18A
0x18000d174  mov     rax, [rdi]
0x18000d177  mov     rcx, rdi
0x18000d17a  mov     rax, [rax+10h]
0x18000d17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d183  jmp     short loc_18000D18A
0x18000d185  mov     ebx, 80070057h
0x18000d18a  mov     rcx, [rsp+330h+var_2E0]
0x18000d18f  xor     edi, edi
0x18000d191  test    rcx, rcx
0x18000d194  jz      short loc_18000D1A7
0x18000d196  mov     rax, [rcx]
0x18000d199  mov     rax, [rax+10h]
0x18000d19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1a2  mov     [rsp+330h+var_2E0], rdi
0x18000d1a7  mov     rcx, [rsp+330h+var_2D0]
0x18000d1ac  test    rcx, rcx
0x18000d1af  jz      short loc_18000D1C2
0x18000d1b1  mov     rax, [rcx]
0x18000d1b4  mov     rax, [rax+10h]
0x18000d1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1bd  mov     [rsp+330h+var_2D0], rdi
0x18000d1c2  mov     rcx, [rsp+330h+var_2D8]
0x18000d1c7  test    rcx, rcx
0x18000d1ca  jz      short loc_18000D1DD
0x18000d1cc  mov     rax, [rcx]
0x18000d1cf  mov     rax, [rax+10h]
0x18000d1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
