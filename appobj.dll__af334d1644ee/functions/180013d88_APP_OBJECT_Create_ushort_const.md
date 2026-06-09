# APP_OBJECT::Create(ushort const *)

- ea: `0x180013d88`
- end: `0x180013fff`
- name: `?Create@APP_OBJECT@@QEAAJPEBG@Z`
- size: `631`
- prototype: `__int64 __fastcall(APP_OBJECT *this, const unsigned __int8 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013504`
- `0x180014010`
- `0x180014a40`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x180005ba8`
- `0x180013d88`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall APP_OBJECT::Create(APP_OBJECT *this, const unsigned __int8 *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  unsigned __int16 *v8; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v10; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[32]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+70h] [rbp-90h]
  __int16 v14; // [rsp+74h] [rbp-8Ch]
  int v15; // [rsp+78h] [rbp-88h]
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  __int16 v19; // [rsp+ACh] [rbp-54h]
  int v20; // [rsp+B0h] [rbp-50h]
  __int16 v21; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v22[510]; // [rsp+C2h] [rbp-3Eh] BYREF
  __int16 v23; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v24[510]; // [rsp+2C2h] [rbp+1C2h] BYREF

  v9 = 0;
  v8 = 0;
  v10 = 0;
  memset_0(v22, 0, sizeof(v22));
  v14 = 256;
  v12 = (unsigned __int16 *)&v21;
  v13 = 512;
  v21 = 0;
  v15 = 0;
  memset_0(v24, 0, sizeof(v24));
  v4 = (__int64 *)*((_QWORD *)this + 24);
  v17 = (unsigned __int16 *)&v23;
  v18 = 512;
  v23 = 0;
  v5 = *v4;
  v19 = 256;
  v20 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(v5 + 64))(
         v4,
         L"name",
         &v9,
         0,
         0);
  if ( v6 >= 0 )
  {
    v6 = STRU::Copy((STRU *)v11, (const unsigned __int8 *)v9);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 64LL))(
             *((_QWORD *)this + 23),
             L"path",
             &v8,
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = STRU::Append((STRU *)v11, (const unsigned __int8 *)v8);
        if ( v6 >= 0 )
        {
          v6 = STRU::Copy((STRU *)v16, (const unsigned __int8 *)v12);
          if ( v6 >= 0 )
          {
            v6 = STRU::Copy((APP_OBJECT *)((char *)this + 16), (const unsigned __int8 *)v17);
            if ( v6 >= 0 )
            {
              v6 = COMMAND_OBJECT::AddAttribute(this, L"path", v8);
              if ( v6 >= 0 )
              {
                v6 = COMMAND_OBJECT::AddAttribute(this, L"APP.NAME", v12);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 64LL))(
                         *((_QWORD *)this + 23),
                         L"applicationPool",
                         &v10,
                         0,
                         0);
                  if ( v6 >= 0 )
                  {
                    v6 = COMMAND_OBJECT::AddAttribute(this, L"APPPOOL.NAME", v10);
                    if ( v6 >= 0 )
                    {
                      v6 = COMMAND_OBJECT::AddAttribute(this, L"SITE.NAME", v9);
                      if ( v6 >= 0 )
                      {
                        if ( a2 )
                          v6 = STRU::Copy((APP_OBJECT *)((char *)this + 128), a2);
                        else
                          v6 = -2147024809;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  BUFFER::~BUFFER((BUFFER *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013d88  mov     [rsp-8+arg_10], rbx
0x180013d8d  push    rbp
0x180013d8e  push    rsi
0x180013d8f  push    rdi
0x180013d90  lea     rbp, [rsp-3D0h]
0x180013d98  sub     rsp, 4D0h
0x180013d9f  mov     rax, cs:__security_cookie
0x180013da6  xor     rax, rsp
0x180013da9  mov     [rbp+3E0h+var_20], rax
0x180013db0  mov     rsi, rdx
0x180013db3  mov     [rsp+4E0h+var_4A8], 0
0x180013dbc  mov     rdi, rcx
0x180013dbf  mov     [rsp+4E0h+var_4B0], 0
0x180013dc8  xor     edx, edx; Val
0x180013dca  mov     [rsp+4E0h+var_4A0], 0
0x180013dd3  lea     rcx, [rbp+3E0h+var_41E]; void *
0x180013dd7  mov     r8d, 1FEh; Size
0x180013ddd  call    memset_0
0x180013de2  lea     rax, [rbp+3E0h+var_420]
0x180013de6  mov     [rsp+4E0h+var_46C], 100h
0x180013ded  mov     ebx, 200h
0x180013df2  mov     [rsp+4E0h+var_478], rax
0x180013df7  xor     eax, eax
0x180013df9  mov     [rsp+4E0h+var_470], ebx
0x180013dfd  xor     edx, edx; Val
0x180013dff  mov     [rbp+3E0h+var_420], ax
0x180013e03  lea     rcx, [rbp+3E0h+var_21E]; void *
0x180013e0a  mov     [rsp+4E0h+var_468], 0
0x180013e12  lea     r8d, [rbx-2]; Size
0x180013e16  call    memset_0
0x180013e1b  mov     rcx, [rdi+0C0h]
0x180013e22  lea     rax, [rbp+3E0h+var_220]
0x180013e29  mov     [rbp+3E0h+var_440], rax
0x180013e2d  lea     r8, [rsp+4E0h+var_4A8]
0x180013e32  xor     eax, eax
0x180013e34  mov     [rbp+3E0h+var_438], ebx
0x180013e37  mov     [rbp+3E0h+var_220], ax
0x180013e3e  lea     rdx, aName_0; "name"
0x180013e45  mov     rax, [rcx]
0x180013e48  xor     r9d, r9d
0x180013e4b  mov     [rbp+3E0h+var_434], 100h
0x180013e51  mov     [rbp+3E0h+var_430], 0
0x180013e58  mov     [rsp+4E0h+var_4C0], 0
0x180013e61  mov     rax, [rax+40h]
0x180013e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e6a  mov     ebx, eax
0x180013e6c  test    eax, eax
0x180013e6e  js      loc_180013FC8
0x180013e74  mov     rdx, [rsp+4E0h+var_4A8]; unsigned __int16 *
0x180013e79  lea     rcx, [rsp+4E0h+var_498]; this
0x180013e7e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013e83  mov     ebx, eax
0x180013e85  test    eax, eax
0x180013e87  js      loc_180013FC8
0x180013e8d  mov     rcx, [rdi+0B8h]
0x180013e94  lea     r8, [rsp+4E0h+var_4B0]
0x180013e99  xor     r9d, r9d
0x180013e9c  mov     [rsp+4E0h+var_4C0], 0
0x180013ea5  lea     rdx, aPath_1; "path"
0x180013eac  mov     rax, [rcx]
0x180013eaf  mov     rax, [rax+40h]
0x180013eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb8  mov     ebx, eax
0x180013eba  test    eax, eax
0x180013ebc  js      loc_180013FC8
0x180013ec2  mov     rdx, [rsp+4E0h+var_4B0]; unsigned __int16 *
0x180013ec7  lea     rcx, [rsp+4E0h+var_498]; this
0x180013ecc  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180013ed1  mov     ebx, eax
0x180013ed3  test    eax, eax
0x180013ed5  js      loc_180013FC8
0x180013edb  mov     rdx, [rsp+4E0h+var_478]; unsigned __int16 *
0x180013ee0  lea     rcx, [rbp+3E0h+var_460]; this
0x180013ee4  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013ee9  mov     ebx, eax
0x180013eeb  test    eax, eax
0x180013eed  js      loc_180013FC8
0x180013ef3  mov     rdx, [rbp+3E0h+var_440]; unsigned __int16 *
0x180013ef7  lea     rcx, [rdi+10h]; this
0x180013efb  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013f00  mov     ebx, eax
0x180013f02  test    eax, eax
0x180013f04  js      loc_180013FC8
0x180013f0a  mov     r8, [rsp+4E0h+var_4B0]; unsigned __int16 *
0x180013f0f  lea     rdx, aPath_1; "path"
0x180013f16  mov     rcx, rdi; this
0x180013f19  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180013f1e  mov     ebx, eax
0x180013f20  test    eax, eax
0x180013f22  js      loc_180013FC8
0x180013f28  mov     r8, [rsp+4E0h+var_478]; unsigned __int16 *
0x180013f2d  lea     rdx, aAppName_0; "APP.NAME"
0x180013f34  mov     rcx, rdi; this
0x180013f37  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180013f3c  mov     ebx, eax
0x180013f3e  test    eax, eax
0x180013f40  js      loc_180013FC8
0x180013f46  mov     rcx, [rdi+0B8h]
0x180013f4d  lea     r8, [rsp+4E0h+var_4A0]
0x180013f52  xor     r9d, r9d
0x180013f55  mov     [rsp+4E0h+var_4C0], 0
0x180013f5e  lea     rdx, aApplicationpoo_1; "applicationPool"
0x180013f65  mov     rax, [rcx]
0x180013f68  mov     rax, [rax+40h]
0x180013f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f71  mov     ebx, eax
0x180013f73  test    eax, eax
0x180013f75  js      short loc_180013FC8
0x180013f77  mov     r8, [rsp+4E0h+var_4A0]; unsigned __int16 *
0x180013f7c  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x180013f83  mov     rcx, rdi; this
0x180013f86  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180013f8b  mov     ebx, eax
0x180013f8d  test    eax, eax
0x180013f8f  js      short loc_180013FC8
0x180013f91  mov     r8, [rsp+4E0h+var_4A8]; unsigned __int16 *
0x180013f96  lea     rdx, aSiteName; "SITE.NAME"
0x180013f9d  mov     rcx, rdi; this
0x180013fa0  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180013fa5  mov     ebx, eax
0x180013fa7  test    eax, eax
0x180013fa9  js      short loc_180013FC8
0x180013fab  test    rsi, rsi
0x180013fae  jnz     short loc_180013FB7
0x180013fb0  mov     ebx, 80070057h
0x180013fb5  jmp     short loc_180013FC8
0x180013fb7  lea     rcx, [rdi+80h]; this
0x180013fbe  mov     rdx, rsi; unsigned __int16 *
0x180013fc1  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013fc6  mov     ebx, eax
0x180013fc8  lea     rcx, [rbp+3E0h+var_460]; this
0x180013fcc  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013fd1  lea     rcx, [rsp+4E0h+var_498]; this
0x180013fd6  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180013fdb  mov     eax, ebx
0x180013fdd  mov     rcx, [rbp+3E0h+var_20]
0x180013fe4  xor     rcx, rsp; StackCookie
0x180013fe7  call    __security_check_cookie
0x180013fec  mov     rbx, [rsp+4E0h+arg_10]
0x180013ff4  add     rsp, 4D0h
0x180013ffb  pop     rdi
0x180013ffc  pop     rsi
0x180013ffd  pop     rbp
0x180013ffe  retn
```
