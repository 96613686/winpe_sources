# ABO_NODE::MapLocationDeleteKey(void)

- ea: `0x180009fc4`
- end: `0x18000a1b9`
- name: `?MapLocationDeleteKey@ABO_NODE@@AEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009c60`

## callees

- `0x180003460`
- `0x180003f14`
- `0x1800047e4`
- `0x180009fc4`
- `0x18000aaa8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0d6`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18000a14b`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18000a14b`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18000a121`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18000a121`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a012`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a012`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000a0cc`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000a0cc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000a18d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000a18d`

## pseudocode

```c
__int64 __fastcall ABO_NODE::MapLocationDeleteKey(ABO_NODE *this)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  int v4; // r14d
  unsigned int v5; // esi
  int Key; // eax
  signed int LastError; // eax
  const unsigned __int16 *i; // rax
  unsigned int v10; // [rsp+30h] [rbp-19h] BYREF
  const unsigned __int16 *v11; // [rsp+38h] [rbp-11h] BYREF
  __int64 v12; // [rsp+40h] [rbp-9h] BYREF
  HANDLE_ENTRY *v13; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v14[56]; // [rsp+50h] [rbp+7h] BYREF

  v10 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v14);
  v2 = *((_QWORD *)this + 29);
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v2 + 32LL))(v2, &v10);
    if ( v3 >= 0 )
    {
      v4 = 0;
      v5 = 0;
      if ( v10 )
      {
        while ( 1 )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 29) + 40LL))(
                 *((_QWORD *)this + 29),
                 v5,
                 &v12,
                 0);
          if ( v3 < 0 )
            break;
          v3 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v12 + 24LL))(v12, &v11);
          if ( v3 < 0 )
            break;
          Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)g_pPropertySectionTable + 8,
                  v11,
                  &v13);
          if ( Key )
          {
            if ( Key != 2 )
            {
              v3 = -2147467259;
              break;
            }
            v4 = 1;
          }
          else
          {
            HANDLE_ENTRY::DereferenceHandleEntry(v13);
            v13 = 0;
            if ( !MULTISZ::Append((MULTISZ *)v14, v11) )
            {
              LastError = GetLastError();
              v3 = LastError;
              if ( LastError > 0 )
                v3 = (unsigned __int16)LastError | 0x80070000;
              break;
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          ++v5;
          v12 = 0;
          if ( v5 >= v10 )
            goto LABEL_14;
        }
      }
      else
      {
LABEL_14:
        for ( i = MULTISZ::First((MULTISZ *)v14); ; i = MULTISZ::Next((MULTISZ *)v14, v11) )
        {
          v11 = i;
          if ( !i )
            break;
          (*(void (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 29) + 56LL))(
            *((_QWORD *)this + 29),
            i);
        }
        if ( !v4 )
          ABO_NODE::SetLocation(this, 0);
      }
    }
  }
  else
  {
    v3 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009fc4  mov     [rsp-8+arg_8], rbx
0x180009fc9  mov     [rsp-8+arg_10], rsi
0x180009fce  push    rbp
0x180009fcf  push    rdi
0x180009fd0  push    r14
0x180009fd2  lea     rbp, [rsp-47h]
0x180009fd7  sub     rsp, 90h
0x180009fde  mov     rax, cs:__security_cookie
0x180009fe5  xor     rax, rsp
0x180009fe8  mov     [rbp+57h+var_18], rax
0x180009fec  mov     rdi, rcx
0x180009fef  mov     [rbp+57h+var_70], 0
0x180009ff6  lea     rcx, [rbp+57h+var_50]
0x180009ffa  mov     [rbp+57h+var_60], 0
0x18000a002  mov     [rbp+57h+var_68], 0
0x18000a00a  mov     [rbp+57h+var_58], 0
0x18000a012  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000a018  mov     rcx, [rdi+0E8h]
0x18000a01f  test    rcx, rcx
0x18000a022  jnz     short loc_18000A02B
0x18000a024  xor     ebx, ebx
0x18000a026  jmp     loc_18000A16C
0x18000a02b  mov     rax, [rcx]
0x18000a02e  lea     rdx, [rbp+57h+var_70]
0x18000a032  mov     rax, [rax+20h]
0x18000a036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a03b  mov     ebx, eax
0x18000a03d  test    eax, eax
0x18000a03f  js      loc_18000A16C
0x18000a045  xor     r14d, r14d
0x18000a048  xor     esi, esi
0x18000a04a  cmp     [rbp+57h+var_70], esi
0x18000a04d  jbe     loc_18000A11D
0x18000a053  mov     rcx, [rdi+0E8h]
0x18000a05a  lea     r8, [rbp+57h+var_60]
0x18000a05e  xor     r9d, r9d
0x18000a061  mov     edx, esi
0x18000a063  mov     rax, [rcx]
0x18000a066  mov     rax, [rax+28h]
0x18000a06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a06f  mov     ebx, eax
0x18000a071  test    eax, eax
0x18000a073  js      loc_18000A16C
0x18000a079  mov     rcx, [rbp+57h+var_60]
0x18000a07d  lea     rdx, [rbp+57h+var_68]
0x18000a081  mov     rax, [rcx]
0x18000a084  mov     rax, [rax+18h]
0x18000a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08d  mov     ebx, eax
0x18000a08f  test    eax, eax
0x18000a091  js      loc_18000A16C
0x18000a097  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18000a09e  lea     r8, [rbp+57h+var_58]
0x18000a0a2  mov     rdx, [rbp+57h+var_68]
0x18000a0a6  add     rcx, 8
0x18000a0aa  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18000a0af  test    eax, eax
0x18000a0b1  jnz     short loc_18000A0F1
0x18000a0b3  mov     rcx, [rbp+57h+var_58]; this
0x18000a0b7  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000a0bc  mov     rdx, [rbp+57h+var_68]
0x18000a0c0  lea     rcx, [rbp+57h+var_50]
0x18000a0c4  mov     [rbp+57h+var_58], 0
0x18000a0cc  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18000a0d2  test    eax, eax
0x18000a0d4  jnz     short loc_18000A0FA
0x18000a0d6  call    cs:__imp_GetLastError
0x18000a0dc  mov     ebx, eax
0x18000a0de  test    eax, eax
0x18000a0e0  jle     loc_18000A16C
0x18000a0e6  movzx   ebx, ax
0x18000a0e9  or      ebx, 80070000h
0x18000a0ef  jmp     short loc_18000A16C
0x18000a0f1  cmp     eax, 2
0x18000a0f4  jnz     short loc_18000A129
0x18000a0f6  lea     r14d, [rax-1]
0x18000a0fa  mov     rcx, [rbp+57h+var_60]
0x18000a0fe  mov     rax, [rcx]
0x18000a101  mov     rax, [rax+10h]
0x18000a105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a10a  inc     esi
0x18000a10c  mov     [rbp+57h+var_60], 0
0x18000a114  cmp     esi, [rbp+57h+var_70]
0x18000a117  jb      loc_18000A053
0x18000a11d  lea     rcx, [rbp+57h+var_50]
0x18000a121  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18000a127  jmp     short loc_18000A151
0x18000a129  mov     ebx, 80004005h
0x18000a12e  jmp     short loc_18000A16C
0x18000a130  mov     rcx, [rdi+0E8h]
0x18000a137  mov     rax, [rcx]
0x18000a13a  mov     rax, [rax+38h]
0x18000a13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a143  mov     rdx, [rbp+57h+var_68]
0x18000a147  lea     rcx, [rbp+57h+var_50]
0x18000a14b  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x18000a151  mov     [rbp+57h+var_68], rax
0x18000a155  mov     rdx, rax
0x18000a158  test    rax, rax
0x18000a15b  jnz     short loc_18000A130
0x18000a15d  test    r14d, r14d
0x18000a160  jnz     short loc_18000A16C
0x18000a162  xor     edx, edx; struct INativeConfigLocation *
0x18000a164  mov     rcx, rdi; this
0x18000a167  call    ?SetLocation@ABO_NODE@@QEAAXPEAVINativeConfigLocation@@@Z; ABO_NODE::SetLocation(INativeConfigLocation *)
0x18000a16c  mov     rcx, [rbp+57h+var_60]
0x18000a170  test    rcx, rcx
0x18000a173  jz      short loc_18000A189
0x18000a175  mov     rax, [rcx]
0x18000a178  mov     rax, [rax+10h]
0x18000a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a181  mov     [rbp+57h+var_60], 0
0x18000a189  lea     rcx, [rbp+57h+var_50]
0x18000a18d  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000a193  mov     eax, ebx
0x18000a195  mov     rcx, [rbp+57h+var_18]
0x18000a199  xor     rcx, rsp; StackCookie
0x18000a19c  call    __security_check_cookie
0x18000a1a1  lea     r11, [rsp+0A0h+var_10]
0x18000a1a9  mov     rbx, [r11+28h]
0x18000a1ad  mov     rsi, [r11+30h]
0x18000a1b1  mov     rsp, r11
0x18000a1b4  pop     r14
0x18000a1b6  pop     rdi
0x18000a1b7  pop     rbp
0x18000a1b8  retn
```
