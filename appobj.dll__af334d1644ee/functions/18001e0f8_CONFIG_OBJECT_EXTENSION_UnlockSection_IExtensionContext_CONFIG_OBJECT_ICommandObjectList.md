# CONFIG_OBJECT_EXTENSION::UnlockSection(IExtensionContext *,CONFIG_OBJECT *,ICommandObjectList *)

- ea: `0x18001e0f8`
- end: `0x18001e2b9`
- name: `?UnlockSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVCONFIG_OBJECT@@PEAVICommandObjectList@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct CONFIG_OBJECT *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180001044`
- `0x18000557c`
- `0x180006b6c`
- `0x18001e0f8`
- `0x180036010`

## string_xrefs

- `0x18001e190`: `CONFIG.SECTION`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::UnlockSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct CONFIG_OBJECT *a3,
        struct ICommandObjectList *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  STATUS_OBJECT *v9; // rax
  const unsigned __int16 **v10; // rdi
  va_list v12; // [rsp+20h] [rbp-20h] BYREF
  va_list v13; // [rsp+28h] [rbp-18h] BYREF
  va_list Arguments[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF

  v4 = 0;
  v15 = 0;
  v12 = 0;
  v16 = 0;
  v13 = 0;
  *(_OWORD *)Arguments = 0;
  if ( a3 && a2 && a4 )
  {
    v8 = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v15);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v16);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, const unsigned __int16 *, va_list *))(*(_QWORD *)a3 + 80LL))(
               a3,
               L"CONFIG.SECTION",
               &v12);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, const unsigned __int16 *, va_list *))(*(_QWORD *)a3 + 80LL))(
                 a3,
                 L"path",
                 &v13);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 200LL))(v15, 1);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, _QWORD))(*(_QWORD *)a2 + 208LL))(
                     a2,
                     v16,
                     0);
              if ( v8 >= 0 )
              {
                v9 = (STATUS_OBJECT *)operator new(0x110u);
                if ( v9 && (v10 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v9)) != 0 )
                {
                  Arguments[0] = v12;
                  Arguments[1] = v13;
                  v8 = STATUS_OBJECT::Create(v10, 0x417u, Arguments);
                  if ( v8 >= 0 )
                  {
                    v8 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a4 + 24LL))(
                           a4,
                           v10);
                    if ( v8 >= 0 )
                      v8 = 0;
                  }
                  (*((void (__fastcall **)(const unsigned __int16 **))*v10 + 2))(v10);
                }
                else
                {
                  v8 = -2147024888;
                }
              }
            }
          }
        }
      }
    }
    v4 = v15;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e0f8  mov     [rsp-18h+arg_8], rbx
0x18001e0fd  mov     [rsp-18h+arg_18], rsi
0x18001e102  mov     [rsp-18h+arg_0], rcx
0x18001e107  push    rbp
0x18001e108  push    rdi
0x18001e109  push    r14
0x18001e10b  mov     rbp, rsp
0x18001e10e  sub     rsp, 40h
0x18001e112  xor     ecx, ecx
0x18001e114  xorps   xmm0, xmm0
0x18001e117  mov     [rbp+arg_0], rcx
0x18001e11b  mov     r14, r9
0x18001e11e  mov     [rbp+var_20], rcx
0x18001e122  mov     rdi, r8
0x18001e125  mov     [rbp+arg_10], rcx
0x18001e129  mov     rsi, rdx
0x18001e12c  mov     [rbp+var_18], rcx
0x18001e130  movups  xmmword ptr [rbp+Arguments], xmm0
0x18001e134  test    r8, r8
0x18001e137  jz      loc_18001E28E
0x18001e13d  test    rdx, rdx
0x18001e140  jz      loc_18001E28E
0x18001e146  test    r9, r9
0x18001e149  jz      loc_18001E28E
0x18001e14f  mov     rax, [r8]
0x18001e152  lea     rdx, [rbp+arg_0]
0x18001e156  mov     rcx, r8
0x18001e159  mov     rax, [rax+30h]
0x18001e15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e162  mov     ebx, eax
0x18001e164  test    eax, eax
0x18001e166  js      loc_18001E288
0x18001e16c  mov     rax, [rdi]
0x18001e16f  lea     rdx, [rbp+arg_10]
0x18001e173  mov     rcx, rdi
0x18001e176  mov     rax, [rax+28h]
0x18001e17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e17f  mov     ebx, eax
0x18001e181  test    eax, eax
0x18001e183  js      loc_18001E288
0x18001e189  mov     rax, [rdi]
0x18001e18c  lea     r8, [rbp+var_20]
0x18001e190  lea     rdx, aConfigSection; "CONFIG.SECTION"
0x18001e197  mov     rcx, rdi
0x18001e19a  mov     rax, [rax+50h]
0x18001e19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a3  mov     ebx, eax
0x18001e1a5  test    eax, eax
0x18001e1a7  js      loc_18001E288
0x18001e1ad  mov     rax, [rdi]
0x18001e1b0  lea     r8, [rbp+var_18]
0x18001e1b4  lea     rdx, aPath_1; "path"
0x18001e1bb  mov     rcx, rdi
0x18001e1be  mov     rax, [rax+50h]
0x18001e1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c7  mov     ebx, eax
0x18001e1c9  test    eax, eax
0x18001e1cb  js      loc_18001E288
0x18001e1d1  mov     rcx, [rbp+arg_0]
0x18001e1d5  mov     edx, 1
0x18001e1da  mov     rax, [rcx]
0x18001e1dd  mov     rax, [rax+0C8h]
0x18001e1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e9  mov     ebx, eax
0x18001e1eb  test    eax, eax
0x18001e1ed  js      loc_18001E288
0x18001e1f3  mov     rax, [rsi]
0x18001e1f6  xor     r8d, r8d
0x18001e1f9  mov     rdx, [rbp+arg_10]
0x18001e1fd  mov     rcx, rsi
0x18001e200  mov     rax, [rax+0D0h]
0x18001e207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e20c  mov     ebx, eax
0x18001e20e  test    eax, eax
0x18001e210  js      short loc_18001E288
0x18001e212  mov     ecx, 110h; Size
0x18001e217  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e21c  test    rax, rax
0x18001e21f  jz      short loc_18001E283
0x18001e221  mov     rcx, rax; this
0x18001e224  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x18001e229  mov     rdi, rax
0x18001e22c  test    rax, rax
0x18001e22f  jz      short loc_18001E283
0x18001e231  mov     rax, [rbp+var_20]
0x18001e235  lea     r8, [rbp+Arguments]; Arguments
0x18001e239  mov     [rbp+Arguments], rax
0x18001e23d  mov     edx, 417h; dwMessageId
0x18001e242  mov     rax, [rbp+var_18]
0x18001e246  mov     rcx, rdi; this
0x18001e249  mov     [rbp+Arguments+8], rax
0x18001e24d  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x18001e252  mov     ebx, eax
0x18001e254  test    eax, eax
0x18001e256  js      short loc_18001E272
0x18001e258  mov     rax, [r14]
0x18001e25b  mov     rdx, rdi
0x18001e25e  mov     rcx, r14
0x18001e261  mov     rax, [rax+18h]
0x18001e265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e26a  mov     ebx, eax
0x18001e26c  test    eax, eax
0x18001e26e  js      short loc_18001E272
0x18001e270  xor     ebx, ebx
0x18001e272  mov     rax, [rdi]
0x18001e275  mov     rcx, rdi
0x18001e278  mov     rax, [rax+10h]
0x18001e27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e281  jmp     short loc_18001E288
0x18001e283  mov     ebx, 80070008h
0x18001e288  mov     rcx, [rbp+arg_0]
0x18001e28c  jmp     short loc_18001E293
0x18001e28e  mov     ebx, 80070057h
0x18001e293  test    rcx, rcx
0x18001e296  jz      short loc_18001E2A4
0x18001e298  mov     rax, [rcx]
0x18001e29b  mov     rax, [rax+10h]
0x18001e29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a4  mov     rsi, [rsp+40h+arg_18]
0x18001e2a9  mov     eax, ebx
0x18001e2ab  mov     rbx, [rsp+40h+arg_8]
0x18001e2b0  add     rsp, 40h
0x18001e2b4  pop     r14
0x18001e2b6  pop     rdi
0x18001e2b7  pop     rbp
0x18001e2b8  retn
```
