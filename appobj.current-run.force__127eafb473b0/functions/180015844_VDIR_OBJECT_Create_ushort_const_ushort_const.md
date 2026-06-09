# VDIR_OBJECT::Create(ushort const *,ushort const *)

- ea: `0x180015844`
- end: `0x180015aa4`
- name: `?Create@VDIR_OBJECT@@QEAAJPEBG0@Z`
- size: `608`
- prototype: `__int64 __fastcall(VDIR_OBJECT *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015398`
- `0x180015ab0`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180002e90`
- `0x180005ba8`
- `0x180015844`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x18001591b`: `physicalPath`
- `0x18001593d`: `physicalPath`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT::Create(VDIR_OBJECT *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // ebx
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v9; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v10; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+68h] [rbp-98h]
  __int16 v14; // [rsp+6Ch] [rbp-94h]
  int v15; // [rsp+70h] [rbp-90h]
  _BYTE v16[32]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  __int16 v19; // [rsp+A4h] [rbp-5Ch]
  int v20; // [rsp+A8h] [rbp-58h]
  __int16 v21; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v22[510]; // [rsp+B2h] [rbp-4Eh] BYREF
  __int16 v23; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v24[510]; // [rsp+2B2h] [rbp+1B2h] BYREF

  memset_0(v22, 0, sizeof(v22));
  v14 = 256;
  v12 = (unsigned __int16 *)&v21;
  v13 = 512;
  v21 = 0;
  v15 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 512;
  v17 = (unsigned __int16 *)&v23;
  v19 = 256;
  v23 = 0;
  v9 = 0;
  v10 = 0;
  v20 = 0;
  v6 = STRU::Copy((STRU *)v11, a2);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 64LL))(
           *((_QWORD *)this + 23),
           L"physicalPath",
           &v10,
           0,
           0);
    if ( v6 >= 0 )
    {
      v6 = COMMAND_OBJECT::AddAttribute(this, L"physicalPath", v10);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 64LL))(
               *((_QWORD *)this + 23),
               L"path",
               &v9,
               0,
               0);
        if ( v6 >= 0 )
        {
          v6 = COMMAND_OBJECT::AddAttribute(this, L"path", v9);
          if ( v6 >= 0 )
          {
            if ( v12[v15 - 1] == 47 || (v6 = STRU::Append((STRU *)v11, L"/"), v6 >= 0) )
            {
              v7 = v9;
              if ( *v9 == 47 )
                v7 = ++v9;
              v6 = STRU::Append((STRU *)v11, v7);
              if ( v6 >= 0 )
              {
                v6 = STRU::Copy((STRU *)v16, (const struct STRU *)v11);
                if ( v6 >= 0 )
                {
                  v6 = STRU::Copy((VDIR_OBJECT *)((char *)this + 16), v17);
                  if ( v6 >= 0 )
                  {
                    v6 = COMMAND_OBJECT::AddAttribute(this, L"APP.NAME", a2);
                    if ( v6 >= 0 )
                    {
                      v6 = COMMAND_OBJECT::AddAttribute(this, L"VDIR.NAME", v12);
                      if ( v6 >= 0 )
                      {
                        if ( a3 )
                          v6 = STRU::Copy((VDIR_OBJECT *)((char *)this + 128), a3);
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
0x180015844  push    rbp
0x180015846  push    rbx
0x180015847  push    rsi
0x180015848  push    rdi
0x180015849  push    r14
0x18001584b  lea     rbp, [rsp-3C0h]
0x180015853  sub     rsp, 4C0h
0x18001585a  mov     rax, cs:__security_cookie
0x180015861  xor     rax, rsp
0x180015864  mov     [rbp+3E0h+var_30], rax
0x18001586b  mov     rsi, r8
0x18001586e  mov     r14, rdx
0x180015871  mov     rdi, rcx
0x180015874  xor     edx, edx; Val
0x180015876  mov     r8d, 1FEh; Size
0x18001587c  lea     rcx, [rbp+3E0h+var_42E]; void *
0x180015880  call    memset_0
0x180015885  lea     rax, [rbp+3E0h+var_430]
0x180015889  mov     [rsp+4E0h+var_474], 100h
0x180015890  mov     ebx, 200h
0x180015895  mov     [rsp+4E0h+var_480], rax
0x18001589a  xor     eax, eax
0x18001589c  mov     [rsp+4E0h+var_478], ebx
0x1800158a0  xor     edx, edx; Val
0x1800158a2  mov     [rbp+3E0h+var_430], ax
0x1800158a6  lea     rcx, [rbp+3E0h+var_22E]; void *
0x1800158ad  mov     [rsp+4E0h+var_470], 0
0x1800158b5  lea     r8d, [rbx-2]; Size
0x1800158b9  call    memset_0
0x1800158be  lea     rax, [rbp+3E0h+var_230]
0x1800158c5  mov     [rbp+3E0h+var_440], ebx
0x1800158c8  mov     [rbp+3E0h+var_448], rax
0x1800158cc  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800158d1  xor     eax, eax
0x1800158d3  mov     [rbp+3E0h+var_43C], 100h
0x1800158d9  mov     rdx, r14; unsigned __int16 *
0x1800158dc  mov     [rbp+3E0h+var_230], ax
0x1800158e3  mov     [rsp+4E0h+var_4B0], rax
0x1800158e8  mov     [rsp+4E0h+var_4A8], rax
0x1800158ed  mov     [rbp+3E0h+var_438], 0
0x1800158f4  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800158f9  mov     ebx, eax
0x1800158fb  test    eax, eax
0x1800158fd  js      loc_180015A71
0x180015903  mov     rcx, [rdi+0B8h]
0x18001590a  lea     r8, [rsp+4E0h+var_4A8]
0x18001590f  xor     r9d, r9d
0x180015912  mov     [rsp+4E0h+var_4C0], 0
0x18001591b  lea     rdx, aPhysicalpath; "physicalPath"
0x180015922  mov     rax, [rcx]
0x180015925  mov     rax, [rax+40h]
0x180015929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001592e  mov     ebx, eax
0x180015930  test    eax, eax
0x180015932  js      loc_180015A71
0x180015938  mov     r8, [rsp+4E0h+var_4A8]; unsigned __int16 *
0x18001593d  lea     rdx, aPhysicalpath; "physicalPath"
0x180015944  mov     rcx, rdi; this
0x180015947  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001594c  mov     ebx, eax
0x18001594e  test    eax, eax
0x180015950  js      loc_180015A71
0x180015956  mov     rcx, [rdi+0B8h]
0x18001595d  lea     r8, [rsp+4E0h+var_4B0]
0x180015962  xor     r9d, r9d
0x180015965  mov     [rsp+4E0h+var_4C0], 0
0x18001596e  lea     rdx, aPath_1; "path"
0x180015975  mov     rax, [rcx]
0x180015978  mov     rax, [rax+40h]
0x18001597c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015981  mov     ebx, eax
0x180015983  test    eax, eax
0x180015985  js      loc_180015A71
0x18001598b  mov     r8, [rsp+4E0h+var_4B0]; unsigned __int16 *
0x180015990  lea     rdx, aPath_1; "path"
0x180015997  mov     rcx, rdi; this
0x18001599a  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001599f  mov     ebx, eax
0x1800159a1  test    eax, eax
0x1800159a3  js      loc_180015A71
0x1800159a9  mov     ecx, [rsp+4E0h+var_470]
0x1800159ad  mov     rax, [rsp+4E0h+var_480]
0x1800159b2  dec     ecx
0x1800159b4  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x1800159b9  jz      short loc_1800159D6
0x1800159bb  lea     rdx, SubStr; "/"
0x1800159c2  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800159c7  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800159cc  mov     ebx, eax
0x1800159ce  test    eax, eax
0x1800159d0  js      loc_180015A71
0x1800159d6  mov     rdx, [rsp+4E0h+var_4B0]
0x1800159db  cmp     word ptr [rdx], 2Fh ; '/'
0x1800159df  jnz     short loc_1800159EA
0x1800159e1  add     rdx, 2; unsigned __int16 *
0x1800159e5  mov     [rsp+4E0h+var_4B0], rdx
0x1800159ea  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800159ef  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800159f4  mov     ebx, eax
0x1800159f6  test    eax, eax
0x1800159f8  js      short loc_180015A71
0x1800159fa  lea     rdx, [rsp+4E0h+var_4A0]; struct STRU *
0x1800159ff  lea     rcx, [rsp+4E0h+var_468]; this
0x180015a04  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180015a09  mov     ebx, eax
0x180015a0b  test    eax, eax
0x180015a0d  js      short loc_180015A71
0x180015a0f  mov     rdx, [rbp+3E0h+var_448]; unsigned __int16 *
0x180015a13  lea     rcx, [rdi+10h]; this
0x180015a17  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015a1c  mov     ebx, eax
0x180015a1e  test    eax, eax
0x180015a20  js      short loc_180015A71
0x180015a22  mov     r8, r14; unsigned __int16 *
0x180015a25  lea     rdx, aAppName_0; "APP.NAME"
0x180015a2c  mov     rcx, rdi; this
0x180015a2f  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180015a34  mov     ebx, eax
0x180015a36  test    eax, eax
0x180015a38  js      short loc_180015A71
0x180015a3a  mov     r8, [rsp+4E0h+var_480]; unsigned __int16 *
0x180015a3f  lea     rdx, aVdirName; "VDIR.NAME"
0x180015a46  mov     rcx, rdi; this
0x180015a49  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180015a4e  mov     ebx, eax
0x180015a50  test    eax, eax
0x180015a52  js      short loc_180015A71
0x180015a54  test    rsi, rsi
0x180015a57  jnz     short loc_180015A60
0x180015a59  mov     ebx, 80070057h
0x180015a5e  jmp     short loc_180015A71
0x180015a60  lea     rcx, [rdi+80h]; this
0x180015a67  mov     rdx, rsi; unsigned __int16 *
0x180015a6a  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180015a6f  mov     ebx, eax
0x180015a71  lea     rcx, [rsp+4E0h+var_468]; this
0x180015a76  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180015a7b  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180015a80  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180015a85  mov     eax, ebx
0x180015a87  mov     rcx, [rbp+3E0h+var_30]
0x180015a8e  xor     rcx, rsp; StackCookie
0x180015a91  call    __security_check_cookie
0x180015a96  add     rsp, 4C0h
0x180015a9d  pop     r14
0x180015a9f  pop     rdi
0x180015aa0  pop     rsi
0x180015aa1  pop     rbx
0x180015aa2  pop     rbp
0x180015aa3  retn
```
