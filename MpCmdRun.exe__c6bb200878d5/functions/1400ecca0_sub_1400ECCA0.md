# sub_1400ECCA0

- ea: `0x1400ecca0`
- end: `0x1400ecde4`
- name: `sub_1400ECCA0`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140083478`

## callees

- `0x1400367a0`
- `0x1400368dc`
- `0x14009f738`
- `0x1400ec41c`
- `0x1400ec550`
- `0x1400ecb08`
- `0x1400ecca0`
- `0x1400ed030`
- `0x1401203c0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1400ecd85`
- `MpClient!MpFreeMemory` at `0x1400ecd85`
- `KERNEL32!GetCommandLineW` at `0x1400ecd5e`
- `KERNEL32!GetCommandLineW` at `0x1400ecd5e`

## string_xrefs

- `0x1400ecd71`: `%s: Command Line: %s\n Start Time: %s\n\n`

## pseudocode

```c
void __fastcall sub_1400ECCA0(__int64 a1, __int64 a2)
{
  __int64 v3; // r9
  __int64 v4; // rdx
  void *v5; // rax
  void *v6; // rbx
  const wchar_t *v7; // rdi
  __int64 v8; // rbx
  LPWSTR CommandLineW; // rax
  char v10[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]

  v11 = a2;
  if ( !qword_140197B50 )
  {
    *(_QWORD *)v10 = operator new(0x48u);
    sub_1401203C0(*(_QWORD *)v10, 0, 72);
    LOBYTE(v3) = 1;
    v5 = (void *)sub_1400EC41C(*(_QWORD *)v10, v4, a2, v3);
    v6 = qword_140197B50;
    qword_140197B50 = v5;
    if ( v6 )
    {
      sub_1400EC550(v6);
      j_j_j__free_base(v6);
    }
    *(_QWORD *)v10 = 0;
    sub_1400ECB08(v10);
    sub_1400ED030(L"%S", "\n\n-------------------------------------------------------------------------------------\n");
    v7 = L" ";
    v8 = *(_QWORD *)v10;
    if ( *(_QWORD *)v10 )
      v7 = *(const wchar_t **)v10;
    CommandLineW = GetCommandLineW();
    sub_1400ED030(L"%s: Command Line: %s\n Start Time: %s\n\n", L"MpCmdRun", CommandLineW, v7);
    if ( v8 )
      MpFreeMemory(v8);
  }
}

```

## disassembly

```asm
0x1400ecca0  mov     [rsp+arg_0], rbx
0x1400ecca5  mov     [rsp+arg_10], rsi
0x1400eccaa  push    rdi
0x1400eccab  sub     rsp, 50h
0x1400eccaf  mov     rbx, rdx
0x1400eccb2  mov     [rsp+58h+var_20], rdx
0x1400eccb7  cmp     cs:qword_140197B50, 0
0x1400eccbf  jnz     loc_1400ECDD4
0x1400eccc5  mov     esi, 48h ; 'H'
0x1400eccca  mov     ecx, esi; Size
0x1400ecccc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400eccd1  mov     rdi, rax
0x1400eccd4  mov     qword ptr [rsp+58h+var_28], rax
0x1400eccd9  mov     r8d, esi
0x1400eccdc  xor     edx, edx
0x1400eccde  mov     rcx, rax
0x1400ecce1  call    sub_1401203C0
0x1400ecce6  mov     r9b, 1
0x1400ecce9  mov     r8, rbx
0x1400eccec  mov     rcx, rdi
0x1400eccef  call    sub_1400EC41C
0x1400eccf4  nop
0x1400eccf5  mov     rbx, cs:qword_140197B50
0x1400eccfc  mov     cs:qword_140197B50, rax
0x1400ecd03  test    rbx, rbx
0x1400ecd06  jz      short loc_1400ECD1B
0x1400ecd08  mov     rcx, rbx
0x1400ecd0b  call    sub_1400EC550
0x1400ecd10  mov     edx, esi
0x1400ecd12  mov     rcx, rbx; Block
0x1400ecd15  call    j_j_j__free_base
0x1400ecd1a  nop
0x1400ecd1b  jmp     short loc_1400ECD25
0x1400ecd1d  mov     eax, dword ptr [rsp+58h+var_28]
0x1400ecd21  test    eax, eax
0x1400ecd23  js      short loc_1400ECD91
0x1400ecd25  mov     qword ptr [rsp+58h+var_28], 0
0x1400ecd2e  lea     rcx, [rsp+58h+var_28]
0x1400ecd33  call    sub_1400ECB08
0x1400ecd38  lea     rdx, asc_140168A60; "\n\n-----------------------------------"...
0x1400ecd3f  lea     rcx, aS_6; "%S"
0x1400ecd46  call    sub_1400ED030
0x1400ecd4b  lea     rdi, asc_140146F48; " "
0x1400ecd52  mov     rbx, qword ptr [rsp+58h+var_28]
0x1400ecd57  test    rbx, rbx
0x1400ecd5a  cmovnz  rdi, rbx
0x1400ecd5e  call    cs:GetCommandLineW
0x1400ecd64  mov     r9, rdi
0x1400ecd67  mov     r8, rax
0x1400ecd6a  lea     rdx, aMpcmdrun; "MpCmdRun"
0x1400ecd71  lea     rcx, aSCommandLineSS; "%s: Command Line: %s\n Start Time: %s\n"...
0x1400ecd78  call    sub_1400ED030
0x1400ecd7d  test    rbx, rbx
0x1400ecd80  jz      short loc_1400ECDD4
0x1400ecd82  mov     rcx, rbx
0x1400ecd85  call    cs:__imp_MpFreeMemory
0x1400ecd8b  jmp     short loc_1400ECDD4
0x1400ecd8d  mov     eax, dword ptr [rsp+58h+var_28]
0x1400ecd91  lea     rdx, off_14018DE50
0x1400ecd98  mov     rcx, cs:off_14018DE50
0x1400ecd9f  cmp     rcx, rdx
0x1400ecda2  jz      short loc_1400ECDD4
0x1400ecda4  test    byte ptr [rcx+1Ch], 1
0x1400ecda8  jz      short loc_1400ECDD4
0x1400ecdaa  mov     edx, 19h
0x1400ecdaf  mov     dword ptr [rsp+58h+var_30], eax; char
0x1400ecdb3  mov     rax, [rsp+58h+var_20]
0x1400ecdb8  mov     [rsp+58h+var_38], rax; __int64
0x1400ecdbd  lea     r9, aMpcmdrun; "MpCmdRun"
0x1400ecdc4  lea     r8, qword_140168C68
0x1400ecdcb  mov     rcx, [rcx+10h]; LoggerHandle
0x1400ecdcf  call    sub_14009F738
0x1400ecdd4  mov     rbx, [rsp+58h+arg_0]
0x1400ecdd9  mov     rsi, [rsp+58h+arg_10]
0x1400ecdde  add     rsp, 50h
0x1400ecde2  pop     rdi
0x1400ecde3  retn
```
