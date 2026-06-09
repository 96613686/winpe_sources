# CRegUtils::RegReadStringValueNoThrow(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180011d60`
- end: `0x180011e8b`
- name: `?RegReadStringValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800137d8`

## callees

- `0x18000a704`
- `0x180011d60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011da9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011da9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e67`

## string_xrefs

- `0x180011da0`: `ChannelAccess`
- `0x180011e5b`: `ChannelAccess`

## pseudocode

```c
LSTATUS __fastcall CRegUtils::RegReadStringValueNoThrow(HKEY hkey, __int64 a2, _QWORD *a3)
{
  LSTATUS result; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  _QWORD *v8; // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // r8
  _WORD *v11; // rdi
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+5Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  pcbData = 0;
  result = RegGetValueW(hkey, 0, L"ChannelAccess", 2u, 0, 0, &pcbData);
  if ( !result )
  {
    v6 = pcbData;
    v7 = a3[2];
    if ( pcbData > v7 )
    {
      v9 = pcbData - v7;
      if ( v9 > a3[3] - v7 )
      {
        try
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(a3);
        }
        catch ( std::exception )
        {
          return 14;
        }
      }
      else
      {
        a3[2] = pcbData;
        if ( a3[3] <= 7u )
          v10 = a3;
        else
          v10 = (_QWORD *)*a3;
        v11 = (_WORD *)v10 + v7;
        if ( v9 )
        {
          while ( v9 )
          {
            *v11++ = 0;
            --v9;
          }
        }
        *((_WORD *)v10 + v6) = 0;
      }
    }
    else
    {
      a3[2] = pcbData;
      if ( a3[3] <= 7u )
        v8 = a3;
      else
        v8 = (_QWORD *)*a3;
      *((_WORD *)v8 + v6) = 0;
    }
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    return RegGetValueW(hkey, 0, L"ChannelAccess", 0x10000006u, 0, a3, &pcbData);
  }
  return result;
}

```

## disassembly

```asm
0x180011d60  mov     r11, rsp
0x180011d63  mov     [r11+8], rbx
0x180011d67  mov     [r11+18h], rsi
0x180011d6b  mov     [r11+10h], rdx
0x180011d6f  push    rdi
0x180011d70  sub     rsp, 40h
0x180011d74  mov     rbx, r8
0x180011d77  mov     rsi, rcx
0x180011d7a  mov     [rsp+48h+arg_8], 0
0x180011d82  lea     rax, [r11+10h]
0x180011d86  mov     [r11-18h], rax
0x180011d8a  mov     qword ptr [r11-20h], 0
0x180011d92  mov     qword ptr [r11-28h], 0
0x180011d9a  mov     r9d, 2; dwFlags
0x180011da0  lea     r8, aChannelaccess; "ChannelAccess"
0x180011da7  xor     edx, edx; lpSubKey
0x180011da9  call    cs:__imp_RegGetValueW
0x180011db0  nop     dword ptr [rax+rax+00h]
0x180011db5  test    eax, eax
0x180011db7  jnz     loc_180011E7A
0x180011dbd  mov     edx, [rsp+48h+arg_8]
0x180011dc1  mov     rdi, [rbx+10h]
0x180011dc5  cmp     rdx, rdi
0x180011dc8  ja      short loc_180011DE5
0x180011dca  mov     [rbx+10h], rdx
0x180011dce  cmp     qword ptr [rbx+18h], 7
0x180011dd3  jbe     short loc_180011DDA
0x180011dd5  mov     rcx, [rbx]
0x180011dd8  jmp     short loc_180011DDD
0x180011dda  mov     rcx, rbx
0x180011ddd  xor     eax, eax
0x180011ddf  mov     [rcx+rdx*2], ax
0x180011de3  jmp     short loc_180011E33
0x180011de5  mov     rcx, rdx
0x180011de8  sub     rcx, rdi
0x180011deb  mov     rax, [rbx+18h]
0x180011def  sub     rax, rdi
0x180011df2  cmp     rcx, rax
0x180011df5  ja      short loc_180011E24
0x180011df7  mov     [rbx+10h], rdx
0x180011dfb  cmp     qword ptr [rbx+18h], 7
0x180011e00  jbe     short loc_180011E07
0x180011e02  mov     r8, [rbx]
0x180011e05  jmp     short loc_180011E0A
0x180011e07  mov     r8, rbx
0x180011e0a  lea     rdi, [r8+rdi*2]
0x180011e0e  test    rcx, rcx
0x180011e11  jz      short loc_180011E1B
0x180011e13  xor     eax, eax
0x180011e15  movzx   eax, ax
0x180011e18  rep stosw
0x180011e1b  xor     eax, eax
0x180011e1d  mov     [r8+rdx*2], ax
0x180011e22  jmp     short loc_180011E33
0x180011e24  mov     r9, rcx
0x180011e27  mov     rdx, rcx
0x180011e2a  mov     rcx, rbx; Src
0x180011e2d  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180011e32  nop
0x180011e33  cmp     qword ptr [rbx+18h], 7
0x180011e38  jbe     short loc_180011E3D
0x180011e3a  mov     rbx, [rbx]
0x180011e3d  lea     rax, [rsp+48h+arg_8]
0x180011e42  mov     [rsp+48h+pcbData], rax; pcbData
0x180011e47  mov     [rsp+48h+pvData], rbx; pvData
0x180011e4c  mov     [rsp+48h+pdwType], 0; pdwType
0x180011e55  mov     r9d, 10000006h; dwFlags
0x180011e5b  lea     r8, aChannelaccess; "ChannelAccess"
0x180011e62  xor     edx, edx; lpSubKey
0x180011e64  mov     rcx, rsi; hkey
0x180011e67  call    cs:__imp_RegGetValueW
0x180011e6e  nop     dword ptr [rax+rax+00h]
0x180011e73  jmp     short loc_180011E7A
0x180011e75  mov     eax, 0Eh
0x180011e7a  mov     rbx, [rsp+48h+arg_0]
0x180011e7f  mov     rsi, [rsp+48h+arg_10]
0x180011e84  add     rsp, 40h
0x180011e88  pop     rdi
0x180011e89  retn
```
