# RegistryKey::GetValue(ushort const *,ulong)

- ea: `0x180020930`
- end: `0x180020a99`
- name: `?GetValue@RegistryKey@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGK@Z`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180005000`
- `0x180005750`
- `0x18000d8f8`
- `0x180013294`
- `0x180013860`
- `0x180020930`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180020a6a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020a6a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020986`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020a0f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020986`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020a0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryKey::GetValue(__int64 a1, __int64 a2, const WCHAR *a3, DWORD a4)
{
  HKEY v8; // rcx
  int v9; // eax
  bool v10; // sf
  void *pvData; // rdi
  int ValueW; // eax
  bool v13; // sf
  int pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h]
  void *v17; // [rsp+50h] [rbp-28h]
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF

  v16 = -2;
  v8 = *(HKEY *)(a1 + 64);
  if ( !v8 || (pcbData = 0, v9 = RegGetValueW(v8, 0, a3, a4, 0, 0, &pcbData), v9 == 2) )
  {
    std::wstring::wstring(a2, &qword_18002C640);
  }
  else
  {
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( v10 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
    v17 = pvData;
    ValueW = RegGetValueW(*(HKEY *)(a1 + 64), 0, a3, a4, 0, pvData, &pcbData);
    v13 = ValueW < 0;
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v13 = ValueW < 0;
    }
    if ( v13 )
    {
      pExceptionObject = ValueW;
      throw (long *)&pExceptionObject;
    }
    *(_QWORD *)(a2 + 24) = 7;
    std::wstring::_Eos(a2, 0);
    std::wstring::assign(a2, pvData);
    operator delete[](pvData);
  }
  return a2;
}

```

## disassembly

```asm
0x180020930  mov     r11, rsp
0x180020933  push    rsi
0x180020934  push    rdi
0x180020935  push    r14
0x180020937  sub     rsp, 60h
0x18002093b  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFEh
0x180020943  mov     [r11+10h], rbx
0x180020947  mov     [r11+18h], rbp
0x18002094b  mov     ebp, r9d
0x18002094e  mov     r14, r8
0x180020951  mov     rbx, rdx
0x180020954  mov     rsi, rcx
0x180020957  mov     rcx, [rcx+40h]; hkey
0x18002095b  test    rcx, rcx
0x18002095e  jz      loc_180020A72
0x180020964  mov     dword ptr [r11+8], 0
0x18002096c  lea     rax, [r11+8]
0x180020970  mov     [r11-48h], rax
0x180020974  mov     qword ptr [r11-50h], 0
0x18002097c  mov     qword ptr [r11-58h], 0
0x180020984  xor     edx, edx; lpSubKey
0x180020986  call    cs:__imp_RegGetValueW
0x18002098c  cmp     eax, 2
0x18002098f  jz      loc_180020A72
0x180020995  test    eax, eax
0x180020997  jle     short loc_1800209A3
0x180020999  movzx   eax, ax
0x18002099c  or      eax, 80070000h
0x1800209a1  test    eax, eax
0x1800209a3  jns     short loc_1800209BB
0x1800209a5  mov     [rsp+78h+pExceptionObject], eax
0x1800209a9  lea     rdx, _TI1J; pThrowInfo
0x1800209b0  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800209b5  call    _CxxThrowException_0
0x1800209bb  mov     ecx, [rsp+78h+arg_0]
0x1800209c2  shr     rcx, 1
0x1800209c5  mov     eax, 2
0x1800209ca  mul     rcx
0x1800209cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800209d4  cmovb   rax, rcx
0x1800209d8  mov     rcx, rax; unsigned __int64
0x1800209db  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800209e0  mov     rdi, rax
0x1800209e3  mov     [rsp+78h+var_28], rax
0x1800209e8  lea     rax, [rsp+78h+arg_0]
0x1800209f0  mov     [rsp+78h+pcbData], rax; pcbData
0x1800209f5  mov     [rsp+78h+pvData], rdi; pvData
0x1800209fa  mov     [rsp+78h+pdwType], 0; pdwType
0x180020a03  mov     r9d, ebp; dwFlags
0x180020a06  mov     r8, r14; lpValue
0x180020a09  xor     edx, edx; lpSubKey
0x180020a0b  mov     rcx, [rsi+40h]; hkey
0x180020a0f  call    cs:__imp_RegGetValueW
0x180020a15  test    eax, eax
0x180020a17  jle     short loc_180020A23
0x180020a19  movzx   eax, ax
0x180020a1c  or      eax, 80070000h
0x180020a21  test    eax, eax
0x180020a23  jns     short loc_180020A3B
0x180020a25  mov     [rsp+78h+pExceptionObject], eax
0x180020a29  lea     rdx, _TI1J; pThrowInfo
0x180020a30  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180020a35  call    _CxxThrowException_0
0x180020a3b  mov     r8d, [rsp+78h+arg_0]
0x180020a43  shr     r8, 1
0x180020a46  dec     r8
0x180020a49  mov     qword ptr [rbx+18h], 7
0x180020a51  xor     edx, edx
0x180020a53  mov     rcx, rbx
0x180020a56  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180020a5b  mov     rdx, rdi
0x180020a5e  mov     rcx, rbx
0x180020a61  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180020a66  nop
0x180020a67  mov     rcx, rdi
0x180020a6a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180020a70  jmp     short loc_180020A81
0x180020a72  lea     rdx, qword_18002C640
0x180020a79  mov     rcx, rbx
0x180020a7c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180020a81  mov     rax, rbx
0x180020a84  lea     r11, [rsp+78h+var_18]
0x180020a89  mov     rbx, [r11+28h]
0x180020a8d  mov     rbp, [r11+30h]
0x180020a91  mov     rsp, r11
0x180020a94  pop     r14
0x180020a96  pop     rdi
0x180020a97  pop     rsi
0x180020a98  retn
```
