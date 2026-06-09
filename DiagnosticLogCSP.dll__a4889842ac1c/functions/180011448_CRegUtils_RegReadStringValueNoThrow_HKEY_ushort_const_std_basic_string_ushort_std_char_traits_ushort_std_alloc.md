# CRegUtils::RegReadStringValueNoThrow(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180011448`
- end: `0x180011566`
- name: `?RegReadStringValueNoThrow@CRegUtils@@SAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012ddc`

## callees

- `0x18000a3e0`
- `0x180011448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011491`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011549`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011491`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011549`

## string_xrefs

- `0x180011488`: `ChannelAccess`
- `0x18001153d`: `ChannelAccess`

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
0x180011448  mov     r11, rsp
0x18001144b  mov     [r11+8], rbx
0x18001144f  mov     [r11+18h], rsi
0x180011453  mov     [r11+10h], rdx
0x180011457  push    rdi
0x180011458  sub     rsp, 40h
0x18001145c  mov     rbx, r8
0x18001145f  mov     rsi, rcx
0x180011462  mov     [rsp+48h+arg_8], 0
0x18001146a  lea     rax, [r11+10h]
0x18001146e  mov     [r11-18h], rax
0x180011472  mov     qword ptr [r11-20h], 0
0x18001147a  mov     qword ptr [r11-28h], 0
0x180011482  mov     r9d, 2; dwFlags
0x180011488  lea     r8, aChannelaccess; "ChannelAccess"
0x18001148f  xor     edx, edx; lpSubKey
0x180011491  call    cs:__imp_RegGetValueW
0x180011497  test    eax, eax
0x180011499  jnz     loc_180011556
0x18001149f  mov     edx, [rsp+48h+arg_8]
0x1800114a3  mov     rdi, [rbx+10h]
0x1800114a7  cmp     rdx, rdi
0x1800114aa  ja      short loc_1800114C7
0x1800114ac  mov     [rbx+10h], rdx
0x1800114b0  cmp     qword ptr [rbx+18h], 7
0x1800114b5  jbe     short loc_1800114BC
0x1800114b7  mov     rcx, [rbx]
0x1800114ba  jmp     short loc_1800114BF
0x1800114bc  mov     rcx, rbx
0x1800114bf  xor     eax, eax
0x1800114c1  mov     [rcx+rdx*2], ax
0x1800114c5  jmp     short loc_180011515
0x1800114c7  mov     rcx, rdx
0x1800114ca  sub     rcx, rdi
0x1800114cd  mov     rax, [rbx+18h]
0x1800114d1  sub     rax, rdi
0x1800114d4  cmp     rcx, rax
0x1800114d7  ja      short loc_180011506
0x1800114d9  mov     [rbx+10h], rdx
0x1800114dd  cmp     qword ptr [rbx+18h], 7
0x1800114e2  jbe     short loc_1800114E9
0x1800114e4  mov     r8, [rbx]
0x1800114e7  jmp     short loc_1800114EC
0x1800114e9  mov     r8, rbx
0x1800114ec  lea     rdi, [r8+rdi*2]
0x1800114f0  test    rcx, rcx
0x1800114f3  jz      short loc_1800114FD
0x1800114f5  xor     eax, eax
0x1800114f7  movzx   eax, ax
0x1800114fa  rep stosw
0x1800114fd  xor     eax, eax
0x1800114ff  mov     [r8+rdx*2], ax
0x180011504  jmp     short loc_180011515
0x180011506  mov     r9, rcx
0x180011509  mov     rdx, rcx
0x18001150c  mov     rcx, rbx; Src
0x18001150f  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180011514  nop
0x180011515  cmp     qword ptr [rbx+18h], 7
0x18001151a  jbe     short loc_18001151F
0x18001151c  mov     rbx, [rbx]
0x18001151f  lea     rax, [rsp+48h+arg_8]
0x180011524  mov     [rsp+48h+pcbData], rax; pcbData
0x180011529  mov     [rsp+48h+pvData], rbx; pvData
0x18001152e  mov     [rsp+48h+pdwType], 0; pdwType
0x180011537  mov     r9d, 10000006h; dwFlags
0x18001153d  lea     r8, aChannelaccess; "ChannelAccess"
0x180011544  xor     edx, edx; lpSubKey
0x180011546  mov     rcx, rsi; hkey
0x180011549  call    cs:__imp_RegGetValueW
0x18001154f  jmp     short loc_180011556
0x180011551  mov     eax, 0Eh
0x180011556  mov     rbx, [rsp+48h+arg_0]
0x18001155b  mov     rsi, [rsp+48h+arg_10]
0x180011560  add     rsp, 40h
0x180011564  pop     rdi
0x180011565  retn
```
