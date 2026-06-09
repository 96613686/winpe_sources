# CONFIG_OBJECT_EXTENSION::LockSection(IExtensionContext *,CONFIG_OBJECT *,ICommandObjectList *)

- ea: `0x18001b188`
- end: `0x18001b349`
- name: `?LockSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVCONFIG_OBJECT@@PEAVICommandObjectList@@@Z`
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
- `0x18001b188`
- `0x180036010`

## string_xrefs

- `0x18001b220`: `CONFIG.SECTION`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::LockSection(
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
            v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 200LL))(v15, 2);
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
                  v8 = STATUS_OBJECT::Create(v10, 0x418u, Arguments);
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
0x18001b188  mov     [rsp-18h+arg_8], rbx
0x18001b18d  mov     [rsp-18h+arg_18], rsi
0x18001b192  mov     [rsp-18h+arg_0], rcx
0x18001b197  push    rbp
0x18001b198  push    rdi
0x18001b199  push    r14
0x18001b19b  mov     rbp, rsp
0x18001b19e  sub     rsp, 40h
0x18001b1a2  xor     ecx, ecx
0x18001b1a4  xorps   xmm0, xmm0
0x18001b1a7  mov     [rbp+arg_0], rcx
0x18001b1ab  mov     r14, r9
0x18001b1ae  mov     [rbp+var_20], rcx
0x18001b1b2  mov     rdi, r8
0x18001b1b5  mov     [rbp+arg_10], rcx
0x18001b1b9  mov     rsi, rdx
0x18001b1bc  mov     [rbp+var_18], rcx
0x18001b1c0  movups  xmmword ptr [rbp+Arguments], xmm0
0x18001b1c4  test    r8, r8
0x18001b1c7  jz      loc_18001B31E
0x18001b1cd  test    rdx, rdx
0x18001b1d0  jz      loc_18001B31E
0x18001b1d6  test    r9, r9
0x18001b1d9  jz      loc_18001B31E
0x18001b1df  mov     rax, [r8]
0x18001b1e2  lea     rdx, [rbp+arg_0]
0x18001b1e6  mov     rcx, r8
0x18001b1e9  mov     rax, [rax+30h]
0x18001b1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f2  mov     ebx, eax
0x18001b1f4  test    eax, eax
0x18001b1f6  js      loc_18001B318
0x18001b1fc  mov     rax, [rdi]
0x18001b1ff  lea     rdx, [rbp+arg_10]
0x18001b203  mov     rcx, rdi
0x18001b206  mov     rax, [rax+28h]
0x18001b20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b20f  mov     ebx, eax
0x18001b211  test    eax, eax
0x18001b213  js      loc_18001B318
0x18001b219  mov     rax, [rdi]
0x18001b21c  lea     r8, [rbp+var_20]
0x18001b220  lea     rdx, aConfigSection; "CONFIG.SECTION"
0x18001b227  mov     rcx, rdi
0x18001b22a  mov     rax, [rax+50h]
0x18001b22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b233  mov     ebx, eax
0x18001b235  test    eax, eax
0x18001b237  js      loc_18001B318
0x18001b23d  mov     rax, [rdi]
0x18001b240  lea     r8, [rbp+var_18]
0x18001b244  lea     rdx, aPath_1; "path"
0x18001b24b  mov     rcx, rdi
0x18001b24e  mov     rax, [rax+50h]
0x18001b252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b257  mov     ebx, eax
0x18001b259  test    eax, eax
0x18001b25b  js      loc_18001B318
0x18001b261  mov     rcx, [rbp+arg_0]
0x18001b265  mov     edx, 2
0x18001b26a  mov     rax, [rcx]
0x18001b26d  mov     rax, [rax+0C8h]
0x18001b274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b279  mov     ebx, eax
0x18001b27b  test    eax, eax
0x18001b27d  js      loc_18001B318
0x18001b283  mov     rax, [rsi]
0x18001b286  xor     r8d, r8d
0x18001b289  mov     rdx, [rbp+arg_10]
0x18001b28d  mov     rcx, rsi
0x18001b290  mov     rax, [rax+0D0h]
0x18001b297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b29c  mov     ebx, eax
0x18001b29e  test    eax, eax
0x18001b2a0  js      short loc_18001B318
0x18001b2a2  mov     ecx, 110h; Size
0x18001b2a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b2ac  test    rax, rax
0x18001b2af  jz      short loc_18001B313
0x18001b2b1  mov     rcx, rax; this
0x18001b2b4  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x18001b2b9  mov     rdi, rax
0x18001b2bc  test    rax, rax
0x18001b2bf  jz      short loc_18001B313
0x18001b2c1  mov     rax, [rbp+var_20]
0x18001b2c5  lea     r8, [rbp+Arguments]; Arguments
0x18001b2c9  mov     [rbp+Arguments], rax
0x18001b2cd  mov     edx, 418h; dwMessageId
0x18001b2d2  mov     rax, [rbp+var_18]
0x18001b2d6  mov     rcx, rdi; this
0x18001b2d9  mov     [rbp+Arguments+8], rax
0x18001b2dd  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x18001b2e2  mov     ebx, eax
0x18001b2e4  test    eax, eax
0x18001b2e6  js      short loc_18001B302
0x18001b2e8  mov     rax, [r14]
0x18001b2eb  mov     rdx, rdi
0x18001b2ee  mov     rcx, r14
0x18001b2f1  mov     rax, [rax+18h]
0x18001b2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2fa  mov     ebx, eax
0x18001b2fc  test    eax, eax
0x18001b2fe  js      short loc_18001B302
0x18001b300  xor     ebx, ebx
0x18001b302  mov     rax, [rdi]
0x18001b305  mov     rcx, rdi
0x18001b308  mov     rax, [rax+10h]
0x18001b30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b311  jmp     short loc_18001B318
0x18001b313  mov     ebx, 80070008h
0x18001b318  mov     rcx, [rbp+arg_0]
0x18001b31c  jmp     short loc_18001B323
0x18001b31e  mov     ebx, 80070057h
0x18001b323  test    rcx, rcx
0x18001b326  jz      short loc_18001B334
0x18001b328  mov     rax, [rcx]
0x18001b32b  mov     rax, [rax+10h]
0x18001b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b334  mov     rsi, [rsp+40h+arg_18]
0x18001b339  mov     eax, ebx
0x18001b33b  mov     rbx, [rsp+40h+arg_8]
0x18001b340  add     rsp, 40h
0x18001b344  pop     r14
0x18001b346  pop     rdi
0x18001b347  pop     rbp
0x18001b348  retn
```
