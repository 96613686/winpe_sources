# Vpath::makeNotContentIndexed(char)

- ea: `0x180093490`
- end: `0x1800935f2`
- name: `?makeNotContentIndexed@Vpath@@QEAAXD@Z`
- size: `354`
- prototype: `void __fastcall(Vpath *__hidden this, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800932f0`
- `0x180093490`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180093551`
- `KERNEL32!GetFileAttributesW` at `0x180093551`
- `KERNEL32!SetFileAttributesW` at `0x1800935a5`
- `KERNEL32!SetFileAttributesW` at `0x1800935a5`
- `KERNEL32!SetFileAttributesA` at `0x1800935ad`
- `KERNEL32!SetFileAttributesA` at `0x1800935ad`
- `KERNEL32!GetFileAttributesA` at `0x180093559`
- `KERNEL32!GetFileAttributesA` at `0x180093559`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vpath::makeNotContentIndexed(Vpath *this, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int16 v7; // cx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // ecx
  DWORD FileAttributesW; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  DWORD v16; // ebx
  int v17; // ecx
  BOOL v18; // eax
  _WORD v19[256]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+238h] [rbp+130h]
  int v21; // [rsp+240h] [rbp+138h]
  char v22; // [rsp+244h] [rbp+13Ch]

  if ( Vpath::hasAcls(this) )
  {
    v7 = (unsigned __int8)sub_180096770(v5, v4, v6) ? *(_WORD *)(qword_1802B00B0 + 12) : 0;
    if ( v7 >= 5 )
    {
      lpFileName = v19;
      v21 = 512;
      v19[0] = 0;
      v22 = 0;
      sub_1800B7B38((VstackStrLCP *)v19);
      if ( (unsigned __int8)sub_180096770(v9, v8, v10) )
        v11 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v11 = 0;
      if ( v11 == 2 )
        FileAttributesW = GetFileAttributesW(lpFileName);
      else
        FileAttributesW = GetFileAttributesA((LPCSTR)lpFileName);
      if ( FileAttributesW == -1 )
        goto LABEL_26;
      if ( a2 )
      {
        if ( (FileAttributesW & 0x2000) == 0 )
        {
          v16 = FileAttributesW | 0x2000;
LABEL_18:
          if ( (unsigned __int8)sub_180096770(v14, v13, v15) )
            v17 = *(_DWORD *)(qword_1802B00B0 + 4);
          else
            v17 = 0;
          if ( v17 == 2 )
            v18 = SetFileAttributesW(lpFileName, v16);
          else
            v18 = SetFileAttributesA((LPCSTR)lpFileName, v16);
          if ( v18 )
            Vpath::ClearStat(this);
        }
      }
      else if ( (FileAttributesW & 0x2000) != 0 )
      {
        v16 = FileAttributesW & 0xFFFFDFFF;
        goto LABEL_18;
      }
LABEL_26:
      VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v19);
    }
  }
}

```

## disassembly

```asm
0x180093490  mov     rax, rsp
0x180093493  push    rbp
0x180093494  lea     rbp, [rax-158h]
0x18009349b  sub     rsp, 250h
0x1800934a2  mov     [rsp+250h+var_230], 0FFFFFFFFFFFFFFFEh
0x1800934ab  mov     [rax+10h], rbx
0x1800934af  mov     [rax+18h], rsi
0x1800934b3  mov     [rax+20h], rdi
0x1800934b7  mov     rax, cs:__security_cookie
0x1800934be  xor     rax, rsp
0x1800934c1  mov     [rbp+150h+var_10], rax
0x1800934c8  mov     sil, dl
0x1800934cb  mov     rdi, rcx
0x1800934ce  call    ?hasAcls@Vpath@@QEAADXZ; Vpath::hasAcls(void)
0x1800934d3  test    al, al
0x1800934d5  jz      loc_1800935CA
0x1800934db  call    sub_180096770
0x1800934e0  test    al, al
0x1800934e2  jz      short loc_1800934F1
0x1800934e4  mov     rax, cs:qword_1802B00B0
0x1800934eb  movzx   ecx, word ptr [rax+0Ch]
0x1800934ef  jmp     short loc_1800934F3
0x1800934f1  xor     ecx, ecx
0x1800934f3  cmp     cx, 5
0x1800934f7  jl      loc_1800935CA
0x1800934fd  lea     rax, [rsp+250h+var_220]
0x180093502  mov     [rbp+150h+lpFileName], rax
0x180093509  mov     [rbp+150h+var_18], 200h
0x180093513  and     [rsp+250h+var_220], 0
0x180093519  mov     [rbp+150h+var_14], 0
0x180093520  mov     rdx, rdi
0x180093523  lea     rcx, [rsp+250h+var_220]; this
0x180093528  call    sub_1800B7B38
0x18009352d  nop
0x18009352e  call    sub_180096770
0x180093533  test    al, al
0x180093535  jz      short loc_180093543
0x180093537  mov     rax, cs:qword_1802B00B0
0x18009353e  mov     ecx, [rax+4]
0x180093541  jmp     short loc_180093545
0x180093543  xor     ecx, ecx
0x180093545  cmp     ecx, 2
0x180093548  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x18009354f  jnz     short loc_180093559
0x180093551  call    cs:GetFileAttributesW
0x180093557  jmp     short loc_18009355F
0x180093559  call    cs:GetFileAttributesA
0x18009355f  mov     ebx, eax
0x180093561  cmp     eax, 0FFFFFFFFh
0x180093564  jz      short loc_1800935C0
0x180093566  mov     eax, 2000h
0x18009356b  test    sil, sil
0x18009356e  jz      short loc_180093578
0x180093570  test    eax, ebx
0x180093572  jnz     short loc_1800935C0
0x180093574  or      ebx, eax
0x180093576  jmp     short loc_180093580
0x180093578  test    eax, ebx
0x18009357a  jz      short loc_1800935C0
0x18009357c  btr     ebx, 0Dh
0x180093580  call    sub_180096770
0x180093585  test    al, al
0x180093587  jz      short loc_180093595
0x180093589  mov     rax, cs:qword_1802B00B0
0x180093590  mov     ecx, [rax+4]
0x180093593  jmp     short loc_180093597
0x180093595  xor     ecx, ecx
0x180093597  mov     edx, ebx; dwFileAttributes
0x180093599  cmp     ecx, 2
0x18009359c  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x1800935a3  jnz     short loc_1800935AD
0x1800935a5  call    cs:SetFileAttributesW
0x1800935ab  jmp     short loc_1800935B3
0x1800935ad  call    cs:SetFileAttributesA
0x1800935b3  test    eax, eax
0x1800935b5  jz      short loc_1800935C0
0x1800935b7  mov     rcx, rdi; this
0x1800935ba  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x1800935bf  nop
0x1800935c0  lea     rcx, [rsp+250h+var_220]; this
0x1800935c5  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x1800935ca  mov     rcx, [rbp+150h+var_10]
0x1800935d1  xor     rcx, rsp
0x1800935d4  call    sub_1801503E0
0x1800935d9  lea     r11, [rsp+250h+var_s0]
0x1800935e1  mov     rbx, [r11+18h]
0x1800935e5  mov     rsi, [r11+20h]
0x1800935e9  mov     rdi, [r11+28h]
0x1800935ed  mov     rsp, r11
0x1800935f0  pop     rbp
0x1800935f1  retn
```
