# Vpath::makeHidden(void)

- ea: `0x180093750`
- end: `0x180093893`
- name: `?makeHidden@Vpath@@QEAAPEAVVstatus@@XZ`
- size: `323`
- prototype: `struct Vstatus *__fastcall(Vpath *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180047c50`
- `0x180093750`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800937df`
- `KERNEL32!GetFileAttributesW` at `0x1800937df`
- `KERNEL32!SetFileAttributesW` at `0x180093822`
- `KERNEL32!SetFileAttributesW` at `0x180093822`
- `KERNEL32!SetFileAttributesA` at `0x18009382a`
- `KERNEL32!SetFileAttributesA` at `0x18009382a`
- `KERNEL32!GetFileAttributesA` at `0x1800937e7`
- `KERNEL32!GetFileAttributesA` at `0x1800937e7`
- `KERNEL32!GetLastError` at `0x18009383b`
- `KERNEL32!GetLastError` at `0x18009383b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Vstatus *__fastcall Vpath::makeHidden(Vpath *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // ecx
  DWORD FileAttributesW; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  DWORD v11; // edi
  int v12; // ecx
  BOOL v13; // eax
  char *v14; // rbx
  DWORD LastError; // eax
  _WORD v17[256]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+238h] [rbp+130h]
  int v19; // [rsp+240h] [rbp+138h]
  char v20; // [rsp+244h] [rbp+13Ch]

  lpFileName = v17;
  v19 = 512;
  v2 = 0;
  v17[0] = 0;
  v20 = 0;
  sub_1800B7B38((VstackStrLCP *)v17);
  if ( (unsigned __int8)sub_180096770(v4, v3, v5) )
    v6 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v6 = 0;
  if ( v6 == 2 )
    FileAttributesW = GetFileAttributesW(lpFileName);
  else
    FileAttributesW = GetFileAttributesA((LPCSTR)lpFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 2) == 0 )
  {
    v11 = FileAttributesW | 2;
    if ( (unsigned __int8)sub_180096770(v9, v8, v10) )
      v12 = *(_DWORD *)(qword_1802B00B0 + 4);
    else
      v12 = 0;
    if ( v12 == 2 )
      v13 = SetFileAttributesW(lpFileName, v11);
    else
      v13 = SetFileAttributesA((LPCSTR)lpFileName, v11);
    if ( v13 )
    {
      Vpath::ClearStat(this);
    }
    else
    {
      v14 = (char *)lpFileName;
      LastError = GetLastError();
      v2 = sub_180047C50(0x20051u, LastError, v14);
    }
  }
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v17);
  return (struct Vstatus *)v2;
}

```

## disassembly

```asm
0x180093750  mov     rax, rsp
0x180093753  push    rbp
0x180093754  lea     rbp, [rax-158h]
0x18009375b  sub     rsp, 250h
0x180093762  mov     [rsp+250h+var_230], 0FFFFFFFFFFFFFFFEh
0x18009376b  mov     [rax+10h], rbx
0x18009376f  mov     [rax+18h], rsi
0x180093773  mov     [rax+20h], rdi
0x180093777  mov     rax, cs:__security_cookie
0x18009377e  xor     rax, rsp
0x180093781  mov     [rbp+150h+var_10], rax
0x180093788  mov     rsi, rcx
0x18009378b  lea     rax, [rsp+250h+var_220]
0x180093790  mov     [rbp+150h+lpFileName], rax
0x180093797  mov     [rbp+150h+var_18], 200h
0x1800937a1  xor     ebx, ebx
0x1800937a3  mov     [rsp+250h+var_220], bx
0x1800937a8  mov     [rbp+150h+var_14], bl
0x1800937ae  mov     rdx, rcx
0x1800937b1  lea     rcx, [rsp+250h+var_220]; this
0x1800937b6  call    sub_1800B7B38
0x1800937bb  nop
0x1800937bc  call    sub_180096770
0x1800937c1  test    al, al
0x1800937c3  jz      short loc_1800937D1
0x1800937c5  mov     rax, cs:qword_1802B00B0
0x1800937cc  mov     ecx, [rax+4]
0x1800937cf  jmp     short loc_1800937D3
0x1800937d1  mov     ecx, ebx
0x1800937d3  cmp     ecx, 2
0x1800937d6  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x1800937dd  jnz     short loc_1800937E7
0x1800937df  call    cs:GetFileAttributesW
0x1800937e5  jmp     short loc_1800937ED
0x1800937e7  call    cs:GetFileAttributesA
0x1800937ed  mov     edi, eax
0x1800937ef  cmp     eax, 0FFFFFFFFh
0x1800937f2  jz      short loc_18009385E
0x1800937f4  test    dil, 2
0x1800937f8  jnz     short loc_18009385E
0x1800937fa  or      edi, 2
0x1800937fd  call    sub_180096770
0x180093802  test    al, al
0x180093804  jz      short loc_180093812
0x180093806  mov     rax, cs:qword_1802B00B0
0x18009380d  mov     ecx, [rax+4]
0x180093810  jmp     short loc_180093814
0x180093812  mov     ecx, ebx
0x180093814  mov     edx, edi; dwFileAttributes
0x180093816  cmp     ecx, 2
0x180093819  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x180093820  jnz     short loc_18009382A
0x180093822  call    cs:SetFileAttributesW
0x180093828  jmp     short loc_180093830
0x18009382a  call    cs:SetFileAttributesA
0x180093830  test    eax, eax
0x180093832  jnz     short loc_180093855
0x180093834  mov     rbx, [rbp+150h+lpFileName]
0x18009383b  call    cs:GetLastError
0x180093841  mov     r8, rbx
0x180093844  mov     edx, eax
0x180093846  mov     ecx, 20051h
0x18009384b  call    sub_180047C50
0x180093850  mov     rbx, rax
0x180093853  jmp     short loc_18009385E
0x180093855  mov     rcx, rsi; this
0x180093858  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18009385d  nop
0x18009385e  lea     rcx, [rsp+250h+var_220]; this
0x180093863  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x180093868  mov     rax, rbx
0x18009386b  mov     rcx, [rbp+150h+var_10]
0x180093872  xor     rcx, rsp
0x180093875  call    sub_1801503E0
0x18009387a  lea     r11, [rsp+250h+var_s0]
0x180093882  mov     rbx, [r11+18h]
0x180093886  mov     rsi, [r11+20h]
0x18009388a  mov     rdi, [r11+28h]
0x18009388e  mov     rsp, r11
0x180093891  pop     rbp
0x180093892  retn
```
