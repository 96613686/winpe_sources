# ATL::CRegParser::RegisterBuffer(char *,int)

- ea: `0x180004f3c`
- end: `0x1800050ba`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEADH@Z`
- size: `382`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800050c0`

## callees

- `0x1800048d0`
- `0x180004a4c`
- `0x180004f3c`
- `0x180005408`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180004fbf`
- `KERNEL32!lstrcmpiA` at `0x180004fbf`
- `USER32!CharNextA` at `0x1800050a1`
- `USER32!CharNextA` at `0x1800050a1`
- `ole32!CoTaskMemFree` at `0x180004fd8`
- `ole32!CoTaskMemFree` at `0x180004fd8`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCSTR *this, char *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _BYTE *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-1058h] BYREF
  CHAR String1[4096]; // [rsp+40h] [rbp-1048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (char **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiA(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)(&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8 + 1];
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v10 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
          if ( Token < 0 )
          {
            *this = v10;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextA(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180004f3c  push    rbx
0x180004f3e  push    rbp
0x180004f3f  push    rsi
0x180004f40  push    rdi
0x180004f41  push    r13
0x180004f43  push    r14
0x180004f45  push    r15
0x180004f47  mov     eax, 1050h
0x180004f4c  call    _alloca_probe
0x180004f51  sub     rsp, rax
0x180004f54  mov     rax, cs:__security_cookie
0x180004f5b  xor     rax, rsp
0x180004f5e  mov     [rsp+1088h+var_48], rax
0x180004f66  mov     r15d, r8d
0x180004f69  mov     [rsp+1088h+pv], 0
0x180004f72  lea     r8, [rsp+1088h+pv]; char **
0x180004f77  mov     rdi, rcx
0x180004f7a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEADPEAPEAD@Z; ATL::CRegParser::PreProcessBuffer(char *,char * *)
0x180004f7f  mov     ebx, eax
0x180004f81  test    eax, eax
0x180004f83  js      short loc_180004FE0
0x180004f85  mov     rbp, [rsp+1088h+pv]
0x180004f8a  mov     [rdi], rbp
0x180004f8d  cmp     byte ptr [rbp+0], 0
0x180004f91  jz      short loc_180004FD5
0x180004f93  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAD@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(char *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(char *)'::`2'::map
0x180004f9a  lea     rdx, [rsp+1088h+String1]; char *
0x180004f9f  mov     rcx, rdi; this
0x180004fa2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180004fa7  mov     ebx, eax
0x180004fa9  test    eax, eax
0x180004fab  js      short loc_180004FD5
0x180004fad  xor     ebx, ebx
0x180004faf  movsxd  rsi, ebx
0x180004fb2  lea     rcx, [rsp+1088h+String1]; lpString1
0x180004fb7  add     rsi, rsi
0x180004fba  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004fbf  call    cs:__imp_lstrcmpiA
0x180004fc5  test    eax, eax
0x180004fc7  jz      short loc_180005002
0x180004fc9  inc     ebx
0x180004fcb  cmp     ebx, 0Eh
0x180004fce  jb      short loc_180004FAF
0x180004fd0  mov     ebx, 80020009h
0x180004fd5  mov     rcx, rbp; pv
0x180004fd8  call    cs:__imp_CoTaskMemFree
0x180004fde  mov     eax, ebx
0x180004fe0  mov     rcx, [rsp+1088h+var_48]
0x180004fe8  xor     rcx, rsp; StackCookie
0x180004feb  call    __security_check_cookie
0x180004ff0  add     rsp, 1050h
0x180004ff7  pop     r15
0x180004ff9  pop     r14
0x180004ffb  pop     r13
0x180004ffd  pop     rdi
0x180004ffe  pop     rsi
0x180004fff  pop     rbp
0x180005000  pop     rbx
0x180005001  retn
0x180005002  mov     rsi, [r13+rsi*8+8]
0x180005007  test    rsi, rsi
0x18000500a  jz      short loc_180004FD0
0x18000500c  lea     rdx, [rsp+1088h+String1]; char *
0x180005011  mov     rcx, rdi; this
0x180005014  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180005019  mov     ebx, eax
0x18000501b  test    eax, eax
0x18000501d  js      short loc_180004FD5
0x18000501f  cmp     [rsp+1088h+String1], 7Bh ; '{'
0x180005024  jnz     short loc_180004FD0
0x180005026  mov     [rsp+1088h+var_1068], 0; int
0x18000502e  mov     r8, rsi; HKEY
0x180005031  lea     rdx, [rsp+1088h+String1]; char *
0x180005036  mov     rcx, rdi; this
0x180005039  test    r15d, r15d
0x18000503c  jz      short loc_180005072
0x18000503e  mov     r14, [rdi]
0x180005041  mov     r9d, r15d; int
0x180005044  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x180005049  mov     ebx, eax
0x18000504b  test    eax, eax
0x18000504d  jns     short loc_180005084
0x18000504f  xor     r9d, r9d; int
0x180005052  mov     [rdi], r14
0x180005055  mov     r8, rsi; HKEY
0x180005058  mov     [rsp+1088h+var_1068], 0; int
0x180005060  lea     rdx, [rsp+1088h+String1]; char *
0x180005065  mov     rcx, rdi; this
0x180005068  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x18000506d  jmp     loc_180004FD5
0x180005072  xor     r9d, r9d; int
0x180005075  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x18000507a  mov     ebx, eax
0x18000507c  test    eax, eax
0x18000507e  js      loc_180004FD5
0x180005084  mov     rdx, [rdi]
0x180005087  movsx   ecx, byte ptr [rdx]
0x18000508a  sub     ecx, 9
0x18000508d  jz      short loc_18000509E
0x18000508f  sub     ecx, 1
0x180005092  jz      short loc_18000509E
0x180005094  sub     ecx, 3
0x180005097  jz      short loc_18000509E
0x180005099  cmp     ecx, 13h
0x18000509c  jnz     short loc_1800050AC
0x18000509e  mov     rcx, rdx; lpsz
0x1800050a1  call    cs:__imp_CharNextA
0x1800050a7  mov     [rdi], rax
0x1800050aa  jmp     short loc_180005084
0x1800050ac  cmp     byte ptr [rdx], 0
0x1800050af  jnz     loc_180004F9A
0x1800050b5  jmp     loc_180004FD5
```
