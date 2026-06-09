# CONFIG_OBJECT::Create(ushort const *,ushort const *,ushort const *)

- ea: `0x180018b78`
- end: `0x180018d77`
- name: `?Create@CONFIG_OBJECT@@QEAAJPEBG00@Z`
- size: `511`
- prototype: `__int64 __fastcall(CONFIG_OBJECT *this, const unsigned __int16 *, const unsigned __int8 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018fd0`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180005ba8`
- `0x180018b78`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180018c0d`: `CONFIG.SECTION`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT::Create(
        CONFIG_OBJECT *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r8
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+24h] [rbp-DCh] BYREF
  _BYTE v14[32]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h]
  __int16 v17; // [rsp+54h] [rbp-ACh]
  int v18; // [rsp+58h] [rbp-A8h]
  __int16 v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[510]; // [rsp+62h] [rbp-9Eh] BYREF

  memset_0(v20, 0, sizeof(v20));
  v16 = 512;
  v15 = (unsigned __int16 *)&v19;
  v17 = 256;
  v18 = 0;
  v19 = 0;
  v12 = 0;
  v13 = 0;
  if ( a2 && a3 && a4 )
  {
    v8 = COMMAND_OBJECT::AddAttribute(this, L"CONFIG.SECTION", a2);
    if ( v8 < 0 )
      goto LABEL_22;
    v8 = COMMAND_OBJECT::AddAttribute(this, L"path", a4);
    if ( v8 < 0 )
      goto LABEL_22;
    v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 23) + 192LL))(*((_QWORD *)this + 23), &v12);
    if ( v8 < 0 )
      goto LABEL_22;
    switch ( v12 )
    {
      case 1:
        v9 = L"Allow";
        break;
      case 2:
        v9 = L"Deny";
        break;
      case 3:
        v9 = L"Inherit";
        break;
      default:
        v8 = -2147024883;
LABEL_22:
        BUFFER::~BUFFER((BUFFER *)v14);
        return (unsigned int)v8;
    }
    v8 = COMMAND_OBJECT::AddAttribute(this, L"overrideMode", v9);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 23) + 248LL))(*((_QWORD *)this + 23), &v13);
      if ( v8 >= 0 )
      {
        v10 = L"false";
        if ( !v13 )
          v10 = L"true";
        v8 = COMMAND_OBJECT::AddAttribute(this, L"locked", v10);
        if ( v8 >= 0 )
        {
          v8 = STRU::Copy((CONFIG_OBJECT *)((char *)this + 128), a3);
          if ( v8 >= 0 )
          {
            v8 = STRU::Copy((STRU *)v14, (const unsigned __int8 *)a2);
            if ( v8 >= 0 )
              v8 = STRU::Copy((CONFIG_OBJECT *)((char *)this + 16), (const unsigned __int8 *)v15);
          }
        }
      }
    }
    goto LABEL_22;
  }
  BUFFER::~BUFFER((BUFFER *)v14);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180018b78  push    rbp
0x180018b7a  push    rbx
0x180018b7b  push    rsi
0x180018b7c  push    rdi
0x180018b7d  push    r14
0x180018b7f  push    r15
0x180018b81  lea     rbp, [rsp-178h]
0x180018b89  sub     rsp, 278h
0x180018b90  mov     rax, cs:__security_cookie
0x180018b97  xor     rax, rsp
0x180018b9a  mov     [rbp+1A0h+var_40], rax
0x180018ba1  mov     r14, r8
0x180018ba4  mov     r15, rdx
0x180018ba7  mov     rdi, rcx
0x180018baa  xor     edx, edx; Val
0x180018bac  mov     r8d, 1FEh; Size
0x180018bb2  lea     rcx, [rsp+2A0h+var_23E]; void *
0x180018bb7  mov     rsi, r9
0x180018bba  call    memset_0
0x180018bbf  lea     rax, [rsp+2A0h+var_240]
0x180018bc4  mov     [rsp+2A0h+var_250], 200h
0x180018bcc  mov     [rsp+2A0h+var_258], rax
0x180018bd1  xor     eax, eax
0x180018bd3  mov     [rsp+2A0h+var_24C], 100h
0x180018bda  mov     [rsp+2A0h+var_248], 0
0x180018be2  mov     [rsp+2A0h+var_240], ax
0x180018be7  mov     [rsp+2A0h+var_280], eax
0x180018beb  mov     [rsp+2A0h+var_27C], eax
0x180018bef  test    r15, r15
0x180018bf2  jz      loc_180018D49
0x180018bf8  test    r14, r14
0x180018bfb  jz      loc_180018D49
0x180018c01  test    rsi, rsi
0x180018c04  jz      loc_180018D49
0x180018c0a  mov     r8, r15; unsigned __int16 *
0x180018c0d  lea     rdx, aConfigSection; "CONFIG.SECTION"
0x180018c14  mov     rcx, rdi; this
0x180018c17  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018c1c  mov     ebx, eax
0x180018c1e  test    eax, eax
0x180018c20  js      loc_180018D3B
0x180018c26  mov     r8, rsi; unsigned __int16 *
0x180018c29  lea     rdx, aPath_1; "path"
0x180018c30  mov     rcx, rdi; this
0x180018c33  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018c38  mov     ebx, eax
0x180018c3a  test    eax, eax
0x180018c3c  js      loc_180018D3B
0x180018c42  mov     rcx, [rdi+0B8h]
0x180018c49  lea     rdx, [rsp+2A0h+var_280]
0x180018c4e  mov     rax, [rcx]
0x180018c51  mov     rax, [rax+0C0h]
0x180018c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c5d  mov     ebx, eax
0x180018c5f  test    eax, eax
0x180018c61  js      loc_180018D3B
0x180018c67  mov     ecx, [rsp+2A0h+var_280]
0x180018c6b  sub     ecx, 1
0x180018c6e  jz      short loc_180018C96
0x180018c70  sub     ecx, 1
0x180018c73  jz      short loc_180018C8D
0x180018c75  cmp     ecx, 1
0x180018c78  jz      short loc_180018C84
0x180018c7a  mov     ebx, 8007000Dh
0x180018c7f  jmp     loc_180018D3B
0x180018c84  lea     r8, aInherit; "Inherit"
0x180018c8b  jmp     short loc_180018C9D
0x180018c8d  lea     r8, aDeny; "Deny"
0x180018c94  jmp     short loc_180018C9D
0x180018c96  lea     r8, aAllow; "Allow"
0x180018c9d  lea     rdx, aOverridemode; "overrideMode"
0x180018ca4  mov     rcx, rdi; this
0x180018ca7  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018cac  mov     ebx, eax
0x180018cae  test    eax, eax
0x180018cb0  js      loc_180018D3B
0x180018cb6  mov     rcx, [rdi+0B8h]
0x180018cbd  lea     rdx, [rsp+2A0h+var_27C]
0x180018cc2  mov     rax, [rcx]
0x180018cc5  mov     rax, [rax+0F8h]
0x180018ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cd1  mov     ebx, eax
0x180018cd3  test    eax, eax
0x180018cd5  js      short loc_180018D3B
0x180018cd7  cmp     [rsp+2A0h+var_27C], 0
0x180018cdc  lea     rax, aTrue; "true"
0x180018ce3  lea     r8, aFalse; "false"
0x180018cea  mov     rcx, rdi; this
0x180018ced  cmovz   r8, rax; unsigned __int16 *
0x180018cf1  lea     rdx, aLocked; "locked"
0x180018cf8  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018cfd  mov     ebx, eax
0x180018cff  test    eax, eax
0x180018d01  js      short loc_180018D3B
0x180018d03  lea     rcx, [rdi+80h]; this
0x180018d0a  mov     rdx, r14; unsigned __int16 *
0x180018d0d  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018d12  mov     ebx, eax
0x180018d14  test    eax, eax
0x180018d16  js      short loc_180018D3B
0x180018d18  mov     rdx, r15; unsigned __int16 *
0x180018d1b  lea     rcx, [rsp+2A0h+var_278]; this
0x180018d20  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018d25  mov     ebx, eax
0x180018d27  test    eax, eax
0x180018d29  js      short loc_180018D3B
0x180018d2b  mov     rdx, [rsp+2A0h+var_258]; unsigned __int16 *
0x180018d30  lea     rcx, [rdi+10h]; this
0x180018d34  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018d39  mov     ebx, eax
0x180018d3b  lea     rcx, [rsp+2A0h+var_278]; this
0x180018d40  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018d45  mov     eax, ebx
0x180018d47  jmp     short loc_180018D58
0x180018d49  lea     rcx, [rsp+2A0h+var_278]; this
0x180018d4e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018d53  mov     eax, 80070057h
0x180018d58  mov     rcx, [rbp+1A0h+var_40]
0x180018d5f  xor     rcx, rsp; StackCookie
0x180018d62  call    __security_check_cookie
0x180018d67  add     rsp, 278h
0x180018d6e  pop     r15
0x180018d70  pop     r14
0x180018d72  pop     rdi
0x180018d73  pop     rsi
0x180018d74  pop     rbx
0x180018d75  pop     rbp
0x180018d76  retn
```
