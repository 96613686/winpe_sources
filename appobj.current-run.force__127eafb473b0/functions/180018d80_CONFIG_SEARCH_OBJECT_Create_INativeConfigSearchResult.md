# CONFIG_SEARCH_OBJECT::Create(INativeConfigSearchResult *)

- ea: `0x180018d80`
- end: `0x180018f97`
- name: `?Create@CONFIG_SEARCH_OBJECT@@QEAAJPEAVINativeConfigSearchResult@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(CONFIG_SEARCH_OBJECT *__hidden this, struct INativeConfigSearchResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180019f48`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180005ba8`
- `0x180018d80`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_ltow_s` at `0x180018f7a`
- `msvcrt!_ltow_s` at `0x180018f7a`

## string_xrefs

- `0x180018e85`: `CONFIGSEARCH.PATH`

## pseudocode

```c
__int64 __fastcall CONFIG_SEARCH_OBJECT::Create(CONFIG_SEARCH_OBJECT *this, struct INativeConfigSearchResult *a2)
{
  wchar_t *p_Buffer; // r14
  signed int v5; // ebx
  __int64 v6; // rcx
  errno_t v8; // eax
  int Value; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  __int16 v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+60h] [rbp-A0h]
  _BYTE v16[32]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v17; // [rsp+88h] [rbp-78h]
  int v18; // [rsp+90h] [rbp-70h]
  __int16 v19; // [rsp+94h] [rbp-6Ch]
  int v20; // [rsp+98h] [rbp-68h]
  wchar_t Buffer; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[126]; // [rsp+A2h] [rbp-5Eh] BYREF
  __int16 v23; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v24[510]; // [rsp+122h] [rbp+22h] BYREF

  memset_0(v22, 0, sizeof(v22));
  v18 = 128;
  p_Buffer = &Buffer;
  Buffer = 0;
  v17 = &Buffer;
  v19 = 256;
  v20 = 0;
  memset_0(v24, 0, sizeof(v24));
  v13 = 512;
  v12 = (unsigned __int16 *)&v23;
  v14 = 256;
  v15 = 0;
  v23 = 0;
  v10 = 0;
  Value = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_14;
  }
  v6 = *((_QWORD *)this + 27);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *((_QWORD *)this + 27) = a2;
  (*(void (__fastcall **)(struct INativeConfigSearchResult *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, unsigned __int16 **))(*(_QWORD *)a2 + 24LL))(
         a2,
         &v10);
  if ( v5 >= 0 )
  {
    v5 = COMMAND_OBJECT::AddAttribute(this, L"CONFIGSEARCH.PATH", v10);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, int *))(*(_QWORD *)a2 + 40LL))(a2, &Value);
      if ( v5 >= 0 )
      {
        if ( Value >= 0 )
        {
          STRU::Copy((STRU *)v16, L"0");
          p_Buffer = v17;
LABEL_10:
          v5 = COMMAND_OBJECT::AddAttribute(this, L"status", p_Buffer);
          if ( v5 >= 0 )
          {
            v5 = STRU::Copy((CONFIG_SEARCH_OBJECT *)((char *)this + 128), L"MACHINE/WEBROOT/APPHOST");
            if ( v5 >= 0 )
            {
              v5 = STRU::Copy((STRU *)v11, v10);
              if ( v5 >= 0 )
                v5 = STRU::Copy((CONFIG_SEARCH_OBJECT *)((char *)this + 16), v12);
            }
          }
          goto LABEL_14;
        }
        v8 = _ltow_s(Value, &Buffer, 0x40u, 16);
        v5 = v8;
        if ( !v8 )
          goto LABEL_10;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
      }
    }
  }
LABEL_14:
  BUFFER::~BUFFER((BUFFER *)v11);
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018d80  mov     [rsp-8+arg_10], rbx
0x180018d85  mov     [rsp-8+arg_18], rsi
0x180018d8a  push    rbp
0x180018d8b  push    rdi
0x180018d8c  push    r14
0x180018d8e  lea     rbp, [rsp-230h]
0x180018d96  sub     rsp, 330h
0x180018d9d  mov     rax, cs:__security_cookie
0x180018da4  xor     rax, rsp
0x180018da7  mov     [rbp+240h+var_20], rax
0x180018dae  mov     rsi, rdx
0x180018db1  mov     rdi, rcx
0x180018db4  xor     edx, edx; Val
0x180018db6  lea     rcx, [rbp+240h+var_29E]; void *
0x180018dba  lea     r8d, [rdx+7Eh]; Size
0x180018dbe  call    memset_0
0x180018dc3  xor     eax, eax
0x180018dc5  mov     [rbp+240h+var_2B0], 80h
0x180018dcc  lea     r14, [rbp+240h+Buffer]
0x180018dd0  mov     [rbp+240h+Buffer], ax
0x180018dd4  xor     edx, edx; Val
0x180018dd6  mov     [rbp+240h+var_2B8], r14
0x180018dda  mov     r8d, 1FEh; Size
0x180018de0  mov     [rbp+240h+var_2AC], 100h
0x180018de6  lea     rcx, [rbp+240h+var_21E]; void *
0x180018dea  mov     [rbp+240h+var_2A8], 0
0x180018df1  call    memset_0
0x180018df6  lea     rax, [rbp+240h+var_220]
0x180018dfa  mov     [rsp+340h+var_2E8], 200h
0x180018e02  mov     [rsp+340h+var_2F0], rax
0x180018e07  xor     eax, eax
0x180018e09  mov     [rsp+340h+var_2E4], 100h
0x180018e10  mov     [rsp+340h+var_2E0], 0
0x180018e18  mov     [rbp+240h+var_220], ax
0x180018e1c  mov     [rsp+340h+var_318], rax
0x180018e21  mov     [rsp+340h+Value], eax
0x180018e25  test    rsi, rsi
0x180018e28  jnz     short loc_180018E34
0x180018e2a  mov     ebx, 80070057h
0x180018e2f  jmp     loc_180018F2F
0x180018e34  mov     rcx, [rdi+0D8h]
0x180018e3b  test    rcx, rcx
0x180018e3e  jz      short loc_180018E4C
0x180018e40  mov     rax, [rcx]
0x180018e43  mov     rax, [rax+10h]
0x180018e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e4c  mov     [rdi+0D8h], rsi
0x180018e53  mov     rcx, rsi
0x180018e56  mov     rax, [rsi]
0x180018e59  mov     rax, [rax+8]
0x180018e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e62  mov     rax, [rsi]
0x180018e65  lea     rdx, [rsp+340h+var_318]
0x180018e6a  mov     rcx, rsi
0x180018e6d  mov     rax, [rax+18h]
0x180018e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e76  mov     ebx, eax
0x180018e78  test    eax, eax
0x180018e7a  js      loc_180018F2F
0x180018e80  mov     r8, [rsp+340h+var_318]; unsigned __int16 *
0x180018e85  lea     rdx, aConfigsearchPa; "CONFIGSEARCH.PATH"
0x180018e8c  mov     rcx, rdi; this
0x180018e8f  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018e94  mov     ebx, eax
0x180018e96  test    eax, eax
0x180018e98  js      loc_180018F2F
0x180018e9e  mov     rax, [rsi]
0x180018ea1  lea     rdx, [rsp+340h+Value]
0x180018ea6  mov     rcx, rsi
0x180018ea9  mov     rax, [rax+28h]
0x180018ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb2  mov     ebx, eax
0x180018eb4  test    eax, eax
0x180018eb6  js      short loc_180018F2F
0x180018eb8  mov     ecx, [rsp+340h+Value]; Value
0x180018ebc  test    ecx, ecx
0x180018ebe  js      loc_180018F6C
0x180018ec4  lea     rdx, a0; "0"
0x180018ecb  lea     rcx, [rsp+340h+var_2D8]; this
0x180018ed0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018ed5  mov     r14, [rbp+240h+var_2B8]
0x180018ed9  mov     r8, r14; unsigned __int16 *
0x180018edc  lea     rdx, aStatus; "status"
0x180018ee3  mov     rcx, rdi; this
0x180018ee6  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180018eeb  mov     ebx, eax
0x180018eed  test    eax, eax
0x180018eef  js      short loc_180018F2F
0x180018ef1  lea     rcx, [rdi+80h]; this
0x180018ef8  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180018eff  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018f04  mov     ebx, eax
0x180018f06  test    eax, eax
0x180018f08  js      short loc_180018F2F
0x180018f0a  mov     rdx, [rsp+340h+var_318]; unsigned __int16 *
0x180018f0f  lea     rcx, [rsp+340h+var_310]; this
0x180018f14  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018f19  mov     ebx, eax
0x180018f1b  test    eax, eax
0x180018f1d  js      short loc_180018F2F
0x180018f1f  mov     rdx, [rsp+340h+var_2F0]; unsigned __int16 *
0x180018f24  lea     rcx, [rdi+10h]; this
0x180018f28  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018f2d  mov     ebx, eax
0x180018f2f  lea     rcx, [rsp+340h+var_310]; this
0x180018f34  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018f39  lea     rcx, [rsp+340h+var_2D8]; this
0x180018f3e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018f43  mov     eax, ebx
0x180018f45  mov     rcx, [rbp+240h+var_20]
0x180018f4c  xor     rcx, rsp; StackCookie
0x180018f4f  call    __security_check_cookie
0x180018f54  lea     r11, [rsp+340h+var_10]
0x180018f5c  mov     rbx, [r11+30h]
0x180018f60  mov     rsi, [r11+38h]
0x180018f64  mov     rsp, r11
0x180018f67  pop     r14
0x180018f69  pop     rdi
0x180018f6a  pop     rbp
0x180018f6b  retn
0x180018f6c  mov     r9d, 10h; Radix
0x180018f72  lea     rdx, [rbp+240h+Buffer]; Buffer
0x180018f76  lea     r8d, [r9+30h]; BufferCount
0x180018f7a  call    cs:__imp__ltow_s
0x180018f80  mov     ebx, eax
0x180018f82  test    eax, eax
0x180018f84  jz      loc_180018ED9
0x180018f8a  jle     short loc_180018F2F
0x180018f8c  movzx   ebx, ax
0x180018f8f  or      ebx, 80070000h
0x180018f95  jmp     short loc_180018F2F
```
