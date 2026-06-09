# CONFIG_OBJECT_EXTENSION::DoReset(IExtensionContext *,INativeConfigurationElement *,ushort const *,ushort const *,ICommandObjectList *)

- ea: `0x180019d30`
- end: `0x180019f42`
- name: `?DoReset@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVINativeConfigurationElement@@PEBG2PEAVICommandObjectList@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t *String1, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180001044`
- `0x18000557c`
- `0x180006b6c`
- `0x180019d30`
- `0x18002a250`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019d89`
- `msvcrt!_wcsicmp` at `0x180019d89`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::DoReset(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct INativeConfigurationElement *a3,
        const unsigned __int16 *a4,
        wchar_t *String1,
        struct ICommandObjectList *a6)
{
  __int64 v9; // rax
  int v10; // ebx
  CONFIG_SECTION_WRITER *v11; // rax
  CONFIG_SECTION_WRITER *v12; // rsi
  const unsigned __int16 **v13; // rdi
  __int64 i; // rbp
  struct CONFIG_SECTION_DEFAULT_VALUE *v15; // rdx
  unsigned __int16 *v16; // rax
  int v17; // r8d
  int v18; // ecx
  STATUS_OBJECT *v19; // rax
  const unsigned __int16 **v20; // rax
  va_list Arguments[2]; // [rsp+30h] [rbp-48h] BYREF

  *(_OWORD *)Arguments = 0;
  if ( a2 && a3 && a4 && String1 )
  {
    if ( _wcsicmp(String1, L"MACHINE/WEBROOT/APPHOST") )
    {
      v9 = *(_QWORD *)a2;
      v10 = -2147024809;
      Arguments[0] = (va_list)String1;
      Arguments[1] = (va_list)L"MACHINE/WEBROOT/APPHOST";
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(v9 + 144))(
        a2,
        2147942487LL,
        3221226504LL,
        Arguments,
        0);
    }
    else
    {
      v11 = (CONFIG_SECTION_WRITER *)operator new(0x18u);
      v12 = v11;
      if ( v11 )
      {
        v13 = 0;
        *((_QWORD *)v11 + 1) = a3;
        *(_QWORD *)v11 = &CONFIG_SECTION_WRITER::`vftable';
        if ( a3 )
        {
          v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD *))(*(_QWORD *)a3 + 24LL))(
                  a3,
                  (_QWORD *)v11 + 2);
          if ( v10 >= 0 )
          {
            for ( i = 0; (unsigned int)i < 0x1D9; i = (unsigned int)(i + 1) )
            {
              v15 = (struct CONFIG_SECTION_DEFAULT_VALUE *)(&g_rgConfigSectionDefaultValues + 3 * i);
              v16 = *(unsigned __int16 **)v15;
              do
              {
                v17 = *(unsigned __int16 *)((char *)a4 + (_QWORD)v16 - *(_QWORD *)v15);
                v18 = *v16 - v17;
                if ( v18 )
                  break;
                ++v16;
              }
              while ( v17 );
              if ( !v18 )
              {
                v10 = CONFIG_SECTION_WRITER::WriteValue(v12, v15);
                if ( v10 < 0 )
                  goto LABEL_25;
              }
            }
            v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, wchar_t *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                    a2,
                    String1,
                    0);
            if ( v10 >= 0 )
            {
              v19 = (STATUS_OBJECT *)operator new(0x110u);
              if ( v19 && (v20 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v19), (v13 = v20) != 0) )
              {
                Arguments[0] = (va_list)a4;
                Arguments[1] = 0;
                v10 = STATUS_OBJECT::Create(v20, 0x40Au, Arguments);
                if ( v10 >= 0 )
                  v10 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a6 + 24LL))(
                          a6,
                          v13);
              }
              else
              {
                v10 = -2147024888;
              }
            }
          }
        }
        else
        {
          v10 = -2147024809;
        }
LABEL_25:
        (**(void (__fastcall ***)(CONFIG_SECTION_WRITER *, __int64))v12)(v12, 1);
        if ( v13 )
          (*((void (__fastcall **)(const unsigned __int16 **))*v13 + 2))(v13);
      }
      else
      {
        return (unsigned int)-2147024888;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019d30  push    rbx
0x180019d32  push    rbp
0x180019d33  push    rsi
0x180019d34  push    rdi
0x180019d35  push    r12
0x180019d37  push    r14
0x180019d39  push    r15
0x180019d3b  sub     rsp, 40h
0x180019d3f  xorps   xmm0, xmm0
0x180019d42  mov     r12, r9
0x180019d45  mov     rbx, r8
0x180019d48  mov     r15, rdx
0x180019d4b  movups  xmmword ptr [rsp+78h+Arguments], xmm0
0x180019d50  test    rdx, rdx
0x180019d53  jz      loc_180019F2C
0x180019d59  test    rbx, rbx
0x180019d5c  jz      loc_180019F2C
0x180019d62  test    r9, r9
0x180019d65  jz      loc_180019F2C
0x180019d6b  mov     r14, [rsp+78h+String1]
0x180019d73  test    r14, r14
0x180019d76  jz      loc_180019F2C
0x180019d7c  lea     rdi, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180019d83  mov     rcx, r14; String1
0x180019d86  mov     rdx, rdi; String2
0x180019d89  call    cs:__imp__wcsicmp
0x180019d8f  test    eax, eax
0x180019d91  jz      short loc_180019DCE
0x180019d93  mov     rax, [r15]
0x180019d96  lea     r9, [rsp+78h+Arguments]
0x180019d9b  mov     ebx, 80070057h
0x180019da0  mov     [rsp+78h+Arguments], r14
0x180019da5  mov     r8d, 0C0000408h
0x180019dab  mov     [rsp+78h+Arguments+8], rdi
0x180019db0  mov     edx, ebx
0x180019db2  mov     [rsp+78h+var_58], 0
0x180019dba  mov     rax, [rax+90h]
0x180019dc1  mov     rcx, r15
0x180019dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc9  jmp     loc_180019F31
0x180019dce  mov     ecx, 18h; Size
0x180019dd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019dd8  mov     rsi, rax
0x180019ddb  test    rax, rax
0x180019dde  jz      loc_180019F25
0x180019de4  xor     edi, edi
0x180019de6  mov     [rsi+8], rbx
0x180019dea  lea     rax, ??_7CONFIG_SECTION_WRITER@@6B@; const CONFIG_SECTION_WRITER::`vftable'
0x180019df1  mov     rcx, rbx
0x180019df4  mov     [rsi], rax
0x180019df7  test    rbx, rbx
0x180019dfa  jnz     short loc_180019E06
0x180019dfc  mov     ebx, 80070057h
0x180019e01  jmp     loc_180019EFC
0x180019e06  mov     rax, [rbx]
0x180019e09  lea     rdx, [rsi+10h]
0x180019e0d  mov     rax, [rax+18h]
0x180019e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e16  mov     ebx, eax
0x180019e18  test    eax, eax
0x180019e1a  js      loc_180019EFC
0x180019e20  xor     ebp, ebp
0x180019e22  cmp     ebp, 1D9h
0x180019e28  jnb     short loc_180019E79
0x180019e2a  lea     rax, ?g_rgConfigSectionDefaultValues@@3PAY00UCONFIG_SECTION_DEFAULT_VALUE@@A; CONFIG_SECTION_DEFAULT_VALUE (near * g_rgConfigSectionDefaultValues)[1]
0x180019e31  mov     r9, r12
0x180019e34  lea     rcx, ds:0[rbp*2]
0x180019e3c  add     rcx, rbp
0x180019e3f  lea     rdx, [rax+rcx*8]; struct CONFIG_SECTION_DEFAULT_VALUE *
0x180019e43  mov     rax, [rdx]
0x180019e46  sub     r9, rax
0x180019e49  movzx   ecx, word ptr [rax]
0x180019e4c  movzx   r8d, word ptr [rax+r9]
0x180019e51  sub     ecx, r8d
0x180019e54  jnz     short loc_180019E5F
0x180019e56  add     rax, 2
0x180019e5a  test    r8d, r8d
0x180019e5d  jnz     short loc_180019E49
0x180019e5f  test    ecx, ecx
0x180019e61  jnz     short loc_180019E75
0x180019e63  mov     rcx, rsi; this
0x180019e66  call    ?WriteValue@CONFIG_SECTION_WRITER@@QEAAJPEAUCONFIG_SECTION_DEFAULT_VALUE@@@Z; CONFIG_SECTION_WRITER::WriteValue(CONFIG_SECTION_DEFAULT_VALUE *)
0x180019e6b  mov     ebx, eax
0x180019e6d  test    eax, eax
0x180019e6f  js      loc_180019EFC
0x180019e75  inc     ebp
0x180019e77  jmp     short loc_180019E22
0x180019e79  mov     rax, [r15]
0x180019e7c  xor     r8d, r8d
0x180019e7f  mov     rdx, r14
0x180019e82  mov     rcx, r15
0x180019e85  mov     rax, [rax+0D0h]
0x180019e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e91  mov     ebx, eax
0x180019e93  test    eax, eax
0x180019e95  js      short loc_180019EFC
0x180019e97  mov     ecx, 110h; Size
0x180019e9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019ea1  test    rax, rax
0x180019ea4  jz      short loc_180019EF7
0x180019ea6  mov     rcx, rax; this
0x180019ea9  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180019eae  mov     rdi, rax
0x180019eb1  test    rax, rax
0x180019eb4  jz      short loc_180019EF7
0x180019eb6  lea     r8, [rsp+78h+Arguments]; Arguments
0x180019ebb  mov     [rsp+78h+Arguments], r12
0x180019ec0  mov     edx, 40Ah; dwMessageId
0x180019ec5  mov     [rsp+78h+Arguments+8], 0
0x180019ece  mov     rcx, rax; this
0x180019ed1  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180019ed6  mov     ebx, eax
0x180019ed8  test    eax, eax
0x180019eda  js      short loc_180019EFC
0x180019edc  mov     rcx, [rsp+78h+arg_28]
0x180019ee4  mov     rdx, rdi
0x180019ee7  mov     rax, [rcx]
0x180019eea  mov     rax, [rax+18h]
0x180019eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ef3  mov     ebx, eax
0x180019ef5  jmp     short loc_180019EFC
0x180019ef7  mov     ebx, 80070008h
0x180019efc  mov     rax, [rsi]
0x180019eff  mov     edx, 1
0x180019f04  mov     rcx, rsi
0x180019f07  mov     rax, [rax]
0x180019f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f0f  test    rdi, rdi
0x180019f12  jz      short loc_180019F31
0x180019f14  mov     rax, [rdi]
0x180019f17  mov     rcx, rdi
0x180019f1a  mov     rax, [rax+10h]
0x180019f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f23  jmp     short loc_180019F31
0x180019f25  mov     ebx, 80070008h
0x180019f2a  jmp     short loc_180019F31
0x180019f2c  mov     ebx, 80070057h
0x180019f31  mov     eax, ebx
0x180019f33  add     rsp, 40h
0x180019f37  pop     r15
0x180019f39  pop     r14
0x180019f3b  pop     r12
0x180019f3d  pop     rdi
0x180019f3e  pop     rsi
0x180019f3f  pop     rbp
0x180019f40  pop     rbx
0x180019f41  retn
```
