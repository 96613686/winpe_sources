# Vpath::makeContentIndexed(void)

- ea: `0x180093600`
- end: `0x180093747`
- name: `?makeContentIndexed@Vpath@@QEAAXXZ`
- size: `327`
- prototype: `void __fastcall(Vpath *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800932f0`
- `0x180093600`
- `0x180095100`
- `0x180096770`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800936ba`
- `KERNEL32!GetFileAttributesW` at `0x1800936ba`
- `KERNEL32!SetFileAttributesW` at `0x1800936fe`
- `KERNEL32!SetFileAttributesW` at `0x1800936fe`
- `KERNEL32!SetFileAttributesA` at `0x180093706`
- `KERNEL32!SetFileAttributesA` at `0x180093706`
- `KERNEL32!GetFileAttributesA` at `0x1800936c2`
- `KERNEL32!GetFileAttributesA` at `0x1800936c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vpath::makeContentIndexed(Vpath *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int16 v5; // cx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // ecx
  DWORD FileAttributesW; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD v14; // ebx
  int v15; // ecx
  BOOL v16; // eax
  _WORD v17[256]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+238h] [rbp+130h]
  int v19; // [rsp+240h] [rbp+138h]
  char v20; // [rsp+244h] [rbp+13Ch]

  if ( Vpath::hasAcls(this) )
  {
    v5 = (unsigned __int8)sub_180096770(v3, v2, v4) ? *(_WORD *)(qword_1802B00B0 + 12) : 0;
    if ( v5 >= 5 )
    {
      lpFileName = v17;
      v19 = 512;
      v17[0] = 0;
      v20 = 0;
      sub_1800B7B38((VstackStrLCP *)v17);
      if ( (unsigned __int8)sub_180096770(v7, v6, v8) )
        v9 = *(_DWORD *)(qword_1802B00B0 + 4);
      else
        v9 = 0;
      if ( v9 == 2 )
        FileAttributesW = GetFileAttributesW(lpFileName);
      else
        FileAttributesW = GetFileAttributesA((LPCSTR)lpFileName);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x2000) != 0 )
      {
        v14 = FileAttributesW & 0xFFFFDFFF;
        if ( (unsigned __int8)sub_180096770(v12, v11, v13) )
          v15 = *(_DWORD *)(qword_1802B00B0 + 4);
        else
          v15 = 0;
        if ( v15 == 2 )
          v16 = SetFileAttributesW(lpFileName, v14);
        else
          v16 = SetFileAttributesA((LPCSTR)lpFileName, v14);
        if ( v16 )
          Vpath::ClearStat(this);
      }
      VstackStrLCP::~VstackStrLCP((VstackStrLCP *)v17);
    }
  }
}

```

## disassembly

```asm
0x180093600  mov     rax, rsp
0x180093603  push    rbp
0x180093604  lea     rbp, [rax-158h]
0x18009360b  sub     rsp, 250h
0x180093612  mov     [rsp+250h+var_230], 0FFFFFFFFFFFFFFFEh
0x18009361b  mov     [rax+10h], rbx
0x18009361f  mov     [rax+18h], rdi
0x180093623  mov     rax, cs:__security_cookie
0x18009362a  xor     rax, rsp
0x18009362d  mov     [rbp+150h+var_10], rax
0x180093634  mov     rdi, rcx
0x180093637  call    ?hasAcls@Vpath@@QEAADXZ; Vpath::hasAcls(void)
0x18009363c  test    al, al
0x18009363e  jz      loc_180093723
0x180093644  call    sub_180096770
0x180093649  test    al, al
0x18009364b  jz      short loc_18009365A
0x18009364d  mov     rax, cs:qword_1802B00B0
0x180093654  movzx   ecx, word ptr [rax+0Ch]
0x180093658  jmp     short loc_18009365C
0x18009365a  xor     ecx, ecx
0x18009365c  cmp     cx, 5
0x180093660  jl      loc_180093723
0x180093666  lea     rax, [rsp+250h+var_220]
0x18009366b  mov     [rbp+150h+lpFileName], rax
0x180093672  mov     [rbp+150h+var_18], 200h
0x18009367c  and     [rsp+250h+var_220], 0
0x180093682  mov     [rbp+150h+var_14], 0
0x180093689  mov     rdx, rdi
0x18009368c  lea     rcx, [rsp+250h+var_220]; this
0x180093691  call    sub_1800B7B38
0x180093696  nop
0x180093697  call    sub_180096770
0x18009369c  test    al, al
0x18009369e  jz      short loc_1800936AC
0x1800936a0  mov     rax, cs:qword_1802B00B0
0x1800936a7  mov     ecx, [rax+4]
0x1800936aa  jmp     short loc_1800936AE
0x1800936ac  xor     ecx, ecx
0x1800936ae  cmp     ecx, 2
0x1800936b1  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x1800936b8  jnz     short loc_1800936C2
0x1800936ba  call    cs:GetFileAttributesW
0x1800936c0  jmp     short loc_1800936C8
0x1800936c2  call    cs:GetFileAttributesA
0x1800936c8  mov     ebx, eax
0x1800936ca  cmp     eax, 0FFFFFFFFh
0x1800936cd  jz      short loc_180093719
0x1800936cf  bt      eax, 0Dh
0x1800936d3  jnb     short loc_180093719
0x1800936d5  btr     ebx, 0Dh
0x1800936d9  call    sub_180096770
0x1800936de  test    al, al
0x1800936e0  jz      short loc_1800936EE
0x1800936e2  mov     rax, cs:qword_1802B00B0
0x1800936e9  mov     ecx, [rax+4]
0x1800936ec  jmp     short loc_1800936F0
0x1800936ee  xor     ecx, ecx
0x1800936f0  mov     edx, ebx; dwFileAttributes
0x1800936f2  cmp     ecx, 2
0x1800936f5  mov     rcx, [rbp+150h+lpFileName]; lpFileName
0x1800936fc  jnz     short loc_180093706
0x1800936fe  call    cs:SetFileAttributesW
0x180093704  jmp     short loc_18009370C
0x180093706  call    cs:SetFileAttributesA
0x18009370c  test    eax, eax
0x18009370e  jz      short loc_180093719
0x180093710  mov     rcx, rdi; this
0x180093713  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x180093718  nop
0x180093719  lea     rcx, [rsp+250h+var_220]; this
0x18009371e  call    ??1VstackStrLCP@@QEAA@XZ_0; VstackStrLCP::~VstackStrLCP(void)
0x180093723  mov     rcx, [rbp+150h+var_10]
0x18009372a  xor     rcx, rsp
0x18009372d  call    sub_1801503E0
0x180093732  lea     r11, [rsp+250h+var_s0]
0x18009373a  mov     rbx, [r11+18h]
0x18009373e  mov     rdi, [r11+20h]
0x180093742  mov     rsp, r11
0x180093745  pop     rbp
0x180093746  retn
```
