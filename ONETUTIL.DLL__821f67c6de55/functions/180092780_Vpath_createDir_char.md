# Vpath::createDir(char)

- ea: `0x180092780`
- end: `0x1800928ed`
- name: `?createDir@Vpath@@QEAAPEAVVstatus@@D@Z`
- size: `365`
- prototype: `struct Vstatus *__fastcall(Vpath *__hidden this, char)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18004f370`
- `0x180091bf0`
- `0x180092190`
- `0x180093f80`
- `0x1800d30f0`
- `0x1800d5e84`

## callees

- `0x180047c50`
- `0x180092780`
- `0x1800939d0`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x180092867`
- `KERNEL32!SetFileAttributesW` at `0x180092867`
- `KERNEL32!SetFileAttributesA` at `0x18009286f`
- `KERNEL32!SetFileAttributesA` at `0x18009286f`
- `KERNEL32!CreateDirectoryW` at `0x180092819`
- `KERNEL32!CreateDirectoryW` at `0x180092819`
- `KERNEL32!CreateDirectoryA` at `0x180092821`
- `KERNEL32!CreateDirectoryA` at `0x180092821`
- `KERNEL32!GetLastError` at `0x18009282e`
- `KERNEL32!GetLastError` at `0x1800928a0`
- `KERNEL32!GetLastError` at `0x18009282e`
- `KERNEL32!GetLastError` at `0x1800928a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Vstatus *__fastcall Vpath::createDir(Vpath *this, char a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // ecx
  BOOL DirectoryW; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  char *v13; // rbx
  DWORD LastError; // eax
  unsigned int v15; // ecx
  int v16; // ecx
  struct Vstatus *v18; // rax
  _WORD v20[256]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpPathName; // [rsp+238h] [rbp+130h]
  int v22; // [rsp+240h] [rbp+138h]
  char v23; // [rsp+244h] [rbp+13Ch]

  Vpath::ClearStat(this);
  lpPathName = v20;
  v22 = 512;
  v4 = 0;
  v20[0] = 0;
  v23 = 0;
  sub_1800B7B38((VstackStrLCP *)v20);
  if ( (unsigned __int8)sub_180096770(v6, v5, v7) )
    v8 = *(_DWORD *)(qword_1802B00B0 + 4);
  else
    v8 = 0;
  if ( v8 == 2 )
    DirectoryW = CreateDirectoryW(lpPathName, 0);
  else
    DirectoryW = CreateDirectoryA((LPCSTR)lpPathName, 0);
  if ( !DirectoryW )
  {
    v13 = *(char **)this;
    LastError = GetLastError();
    v15 = 131075;
LABEL_20:
    v4 = sub_180047C50(v15, LastError, v13);
    goto LABEL_21;
  }
  if ( a2 )
  {
    v16 = (unsigned __int8)sub_180096770(v11, v10, v12) ? *(_DWORD *)(qword_1802B00B0 + 4) : 0;
    if ( !(v16 == 2 ? SetFileAttributesW(lpPathName, 2u) : SetFileAttributesA((LPCSTR)lpPathName, 2u)) )
    {
      v18 = Vpath::removeDir(this);
      if ( v18 )
        (**(void (__fastcall ***)(struct Vstatus *, __int64))v18)(v18, 1);
      v13 = *(char **)this;
      LastError = GetLastError();
      v15 = 131153;
      goto LABEL_20;
    }
  }
LABEL_21:
  VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v20);
  return (struct Vstatus *)v4;
}

```

## disassembly

```asm
0x180092780  mov     rax, rsp
0x180092783  push    rbp
0x180092784  lea     rbp, [rax-158h]
0x18009278b  sub     rsp, 250h
0x180092792  mov     [rsp+250h+var_230], 0FFFFFFFFFFFFFFFEh
0x18009279b  mov     [rax+10h], rbx
0x18009279f  mov     [rax+18h], rsi
0x1800927a3  mov     [rax+20h], rdi
0x1800927a7  mov     rax, cs:__security_cookie
0x1800927ae  xor     rax, rsp
0x1800927b1  mov     [rbp+150h+var_10], rax
0x1800927b8  mov     sil, dl
0x1800927bb  mov     rdi, rcx
0x1800927be  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800927c3  lea     rax, [rsp+250h+var_220]
0x1800927c8  mov     [rbp+150h+lpPathName], rax
0x1800927cf  mov     [rbp+150h+var_18], 200h
0x1800927d9  xor     ebx, ebx
0x1800927db  mov     [rsp+250h+var_220], bx
0x1800927e0  mov     [rbp+150h+var_14], bl
0x1800927e6  mov     rdx, rdi
0x1800927e9  lea     rcx, [rsp+250h+var_220]; this
0x1800927ee  call    sub_1800B7B38
0x1800927f3  nop
0x1800927f4  call    sub_180096770
0x1800927f9  test    al, al
0x1800927fb  jz      short loc_180092809
0x1800927fd  mov     rax, cs:qword_1802B00B0
0x180092804  mov     ecx, [rax+4]
0x180092807  jmp     short loc_18009280B
0x180092809  mov     ecx, ebx
0x18009280b  xor     edx, edx; lpSecurityAttributes
0x18009280d  cmp     ecx, 2
0x180092810  mov     rcx, [rbp+150h+lpPathName]; lpPathName
0x180092817  jnz     short loc_180092821
0x180092819  call    cs:CreateDirectoryW
0x18009281f  jmp     short loc_180092827
0x180092821  call    cs:CreateDirectoryA
0x180092827  test    eax, eax
0x180092829  jnz     short loc_18009283B
0x18009282b  mov     rbx, [rdi]
0x18009282e  call    cs:GetLastError
0x180092834  mov     ecx, 20003h
0x180092839  jmp     short loc_1800928AB
0x18009283b  test    sil, sil
0x18009283e  jz      short loc_1800928B8
0x180092840  call    sub_180096770
0x180092845  test    al, al
0x180092847  jz      short loc_180092855
0x180092849  mov     rax, cs:qword_1802B00B0
0x180092850  mov     ecx, [rax+4]
0x180092853  jmp     short loc_180092857
0x180092855  mov     ecx, ebx
0x180092857  mov     edx, 2; dwFileAttributes
0x18009285c  cmp     ecx, edx
0x18009285e  mov     rcx, [rbp+150h+lpPathName]; lpFileName
0x180092865  jnz     short loc_18009286F
0x180092867  call    cs:SetFileAttributesW
0x18009286d  jmp     short loc_180092875
0x18009286f  call    cs:SetFileAttributesA
0x180092875  test    eax, eax
0x180092877  jnz     short loc_1800928B8
0x180092879  mov     rcx, rdi; this
0x18009287c  call    ?removeDir@Vpath@@QEAAPEAVVstatus@@XZ; Vpath::removeDir(void)
0x180092881  mov     r8, rax
0x180092884  test    rax, rax
0x180092887  jz      short loc_18009289D
0x180092889  mov     rcx, [rax]
0x18009288c  mov     rax, [rcx]
0x18009288f  mov     edx, 1
0x180092894  mov     rcx, r8
0x180092897  call    cs:__guard_dispatch_icall_fptr
0x18009289d  mov     rbx, [rdi]
0x1800928a0  call    cs:GetLastError
0x1800928a6  mov     ecx, 20051h
0x1800928ab  mov     r8, rbx
0x1800928ae  mov     edx, eax
0x1800928b0  call    sub_180047C50
0x1800928b5  mov     rbx, rax
0x1800928b8  lea     rcx, [rsp+250h+var_220]; this
0x1800928bd  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800928c2  mov     rax, rbx
0x1800928c5  mov     rcx, [rbp+150h+var_10]
0x1800928cc  xor     rcx, rsp
0x1800928cf  call    sub_1801503E0
0x1800928d4  lea     r11, [rsp+250h+var_s0]
0x1800928dc  mov     rbx, [r11+18h]
0x1800928e0  mov     rsi, [r11+20h]
0x1800928e4  mov     rdi, [r11+28h]
0x1800928e8  mov     rsp, r11
0x1800928eb  pop     rbp
0x1800928ec  retn
```
