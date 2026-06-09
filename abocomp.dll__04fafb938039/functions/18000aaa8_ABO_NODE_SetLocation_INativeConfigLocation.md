# ABO_NODE::SetLocation(INativeConfigLocation *)

- ea: `0x18000aaa8`
- end: `0x18000ac92`
- name: `?SetLocation@ABO_NODE@@QEAAXPEAVINativeConfigLocation@@@Z`
- size: `490`
- prototype: `void __fastcall(ABO_NODE *__hidden this, struct INativeConfigLocation *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004b80`
- `0x180009ce0`
- `0x180009fc4`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009488`
- `0x18000aaa8`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000abdf`
- `msvcrt!_wcsicmp` at `0x18000abdf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ab07`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ab07`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ac65`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ac65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000abd1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000abd1`

## pseudocode

```c
void __fastcall ABO_NODE::SetLocation(ABO_NODE *this, struct INativeConfigLocation *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rcx
  const wchar_t *Str; // rax
  __int64 v9; // [rsp+20h] [rbp-E0h] BYREF
  int v10; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *String1; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[56]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v13[256]; // [rsp+70h] [rbp-90h] BYREF

  v9 = 0;
  memset_0(v13, 0, sizeof(v13));
  STRU::STRU((STRU *)v12, v13, 0x100u);
  v4 = *((_QWORD *)this + 29);
  String1 = 0;
  v10 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( !a2 )
  {
    v5 = *(_QWORD *)(*((_QWORD *)this + 22) + 32LL);
    if ( (int)ABO_NODE::GetLocationPath(this, (struct STRU *)v12, 0) >= 0
      && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 24LL))(v5, &v10) >= 0 )
    {
      if ( v10 )
      {
        v6 = v10 - 1;
        if ( v10 != 1 )
        {
          while ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 32LL))(v5, v6, &v9) >= 0 )
          {
            v7 = v9;
            if ( v9 )
            {
              if ( (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v9 + 24LL))(v9, &String1) < 0 )
                break;
              Str = STRU::QueryStr((STRU *)v12);
              if ( !_wcsicmp(String1, Str)
                && (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 48LL))(v5, v6) < 0 )
              {
                break;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              v7 = 0;
              v9 = 0;
            }
            if ( !--v6 )
              goto LABEL_17;
          }
        }
      }
    }
  }
  v7 = v9;
LABEL_17:
  *((_QWORD *)this + 29) = a2;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct INativeConfigLocation *))(*(_QWORD *)a2 + 8LL))(a2);
    v7 = v9;
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v9 = 0;
  }
  STRU::~STRU((STRU *)v12);
}

```

## disassembly

```asm
0x18000aaa8  mov     [rsp-8+arg_8], rbx
0x18000aaad  mov     [rsp-8+arg_10], rsi
0x18000aab2  push    rbp
0x18000aab3  push    rdi
0x18000aab4  push    r14
0x18000aab6  lea     rbp, [rsp-180h]
0x18000aabe  sub     rsp, 280h
0x18000aac5  mov     rax, cs:__security_cookie
0x18000aacc  xor     rax, rsp
0x18000aacf  mov     [rbp+190h+var_20], rax
0x18000aad6  mov     rdi, rdx
0x18000aad9  mov     [rsp+290h+var_270], 0
0x18000aae2  mov     r14, rcx
0x18000aae5  xor     edx, edx; Val
0x18000aae7  lea     rcx, [rsp+290h+var_220]; void *
0x18000aaec  mov     r8d, 200h; Size
0x18000aaf2  call    memset_0
0x18000aaf7  mov     r8d, 100h
0x18000aafd  lea     rdx, [rsp+290h+var_220]
0x18000ab02  lea     rcx, [rsp+290h+var_258]
0x18000ab07  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000ab0d  mov     rcx, [r14+0E8h]
0x18000ab14  mov     [rsp+290h+String1], 0
0x18000ab1d  mov     [rsp+290h+var_268], 0
0x18000ab25  test    rcx, rcx
0x18000ab28  jz      short loc_18000AB36
0x18000ab2a  mov     rax, [rcx]
0x18000ab2d  mov     rax, [rax+10h]
0x18000ab31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab36  test    rdi, rdi
0x18000ab39  jnz     loc_18000AC21
0x18000ab3f  mov     rax, [r14+0B0h]
0x18000ab46  lea     rdx, [rsp+290h+var_258]; struct STRU *
0x18000ab4b  xor     r8d, r8d; int
0x18000ab4e  mov     rcx, r14; this
0x18000ab51  mov     rsi, [rax+20h]
0x18000ab55  call    ?GetLocationPath@ABO_NODE@@QEAAJPEAVSTRU@@H@Z; ABO_NODE::GetLocationPath(STRU *,int)
0x18000ab5a  test    eax, eax
0x18000ab5c  js      loc_18000AC21
0x18000ab62  mov     rax, [rsi]
0x18000ab65  lea     rdx, [rsp+290h+var_268]
0x18000ab6a  mov     rcx, rsi
0x18000ab6d  mov     rax, [rax+18h]
0x18000ab71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab76  test    eax, eax
0x18000ab78  js      loc_18000AC21
0x18000ab7e  mov     ebx, [rsp+290h+var_268]
0x18000ab82  test    ebx, ebx
0x18000ab84  jz      loc_18000AC21
0x18000ab8a  sub     ebx, 1
0x18000ab8d  jz      loc_18000AC21
0x18000ab93  mov     rax, [rsi]
0x18000ab96  lea     r8, [rsp+290h+var_270]
0x18000ab9b  mov     edx, ebx
0x18000ab9d  mov     rcx, rsi
0x18000aba0  mov     rax, [rax+20h]
0x18000aba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aba9  test    eax, eax
0x18000abab  js      short loc_18000AC21
0x18000abad  mov     rcx, [rsp+290h+var_270]
0x18000abb2  test    rcx, rcx
0x18000abb5  jz      short loc_18000AC16
0x18000abb7  mov     rax, [rcx]
0x18000abba  lea     rdx, [rsp+290h+String1]
0x18000abbf  mov     rax, [rax+18h]
0x18000abc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc8  test    eax, eax
0x18000abca  js      short loc_18000AC21
0x18000abcc  lea     rcx, [rsp+290h+var_258]
0x18000abd1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000abd7  mov     rcx, [rsp+290h+String1]; String1
0x18000abdc  mov     rdx, rax; String2
0x18000abdf  call    cs:__imp__wcsicmp
0x18000abe5  test    eax, eax
0x18000abe7  jnz     short loc_18000ABFE
0x18000abe9  mov     rax, [rsi]
0x18000abec  mov     edx, ebx
0x18000abee  mov     rcx, rsi
0x18000abf1  mov     rax, [rax+30h]
0x18000abf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abfa  test    eax, eax
0x18000abfc  js      short loc_18000AC21
0x18000abfe  mov     rcx, [rsp+290h+var_270]
0x18000ac03  mov     rax, [rcx]
0x18000ac06  mov     rax, [rax+10h]
0x18000ac0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0f  xor     ecx, ecx
0x18000ac11  mov     [rsp+290h+var_270], rcx
0x18000ac16  add     ebx, 0FFFFFFFFh
0x18000ac19  jnz     loc_18000AB93
0x18000ac1f  jmp     short loc_18000AC26
0x18000ac21  mov     rcx, [rsp+290h+var_270]
0x18000ac26  mov     [r14+0E8h], rdi
0x18000ac2d  test    rdi, rdi
0x18000ac30  jz      short loc_18000AC46
0x18000ac32  mov     rax, [rdi]
0x18000ac35  mov     rcx, rdi
0x18000ac38  mov     rax, [rax+8]
0x18000ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac41  mov     rcx, [rsp+290h+var_270]
0x18000ac46  test    rcx, rcx
0x18000ac49  jz      short loc_18000AC60
0x18000ac4b  mov     rax, [rcx]
0x18000ac4e  mov     rax, [rax+10h]
0x18000ac52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac57  mov     [rsp+290h+var_270], 0
0x18000ac60  lea     rcx, [rsp+290h+var_258]
0x18000ac65  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ac6b  mov     rcx, [rbp+190h+var_20]
0x18000ac72  xor     rcx, rsp; StackCookie
0x18000ac75  call    __security_check_cookie
0x18000ac7a  lea     r11, [rsp+290h+var_10]
0x18000ac82  mov     rbx, [r11+28h]
0x18000ac86  mov     rsi, [r11+30h]
0x18000ac8a  mov     rsp, r11
0x18000ac8d  pop     r14
0x18000ac8f  pop     rdi
0x18000ac90  pop     rbp
0x18000ac91  retn
```
