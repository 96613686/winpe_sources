# SystemSettings::SetAdditionalAnimationSetting(uint)

- ea: `0x140015598`
- end: `0x14001563e`
- name: `?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z`
- size: `166`
- prototype: `__int64 __fastcall(PVOID pvParam)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015644`

## callees

- `0x140015598`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001561c`
- `KERNEL32!GetLastError` at `0x14001561c`
- `USER32!SystemParametersInfoW` at `0x1400155e1`
- `USER32!SystemParametersInfoW` at `0x14001560e`
- `USER32!SystemParametersInfoW` at `0x1400155e1`
- `USER32!SystemParametersInfoW` at `0x14001560e`

## pseudocode

```c
signed int __fastcall SystemSettings::SetAdditionalAnimationSetting(PVOID pvParam)
{
  unsigned __int64 v1; // rdi
  int v2; // ebx
  signed int result; // eax
  UINT uiAction[10]; // [rsp+20h] [rbp-28h]
  int pvParama; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v1 = (unsigned int)pvParam;
  v2 = 0;
  uiAction[0] = 4099;
  uiAction[1] = 4101;
  uiAction[2] = 4103;
  uiAction[3] = 4117;
  uiAction[4] = 4119;
  while ( SystemParametersInfoW(uiAction[v2], 0, (PVOID)v1, 3u) )
  {
    if ( (unsigned int)++v2 >= 5 )
    {
      pvParama = 8;
      v6 = v1;
      if ( SystemParametersInfoW(0x49u, 0, &pvParama, 3u) )
        return 0;
      break;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015598  mov     rax, rsp
0x14001559b  mov     [rax+8], rbx
0x14001559f  mov     [rax+18h], rsi
0x1400155a3  push    rdi
0x1400155a4  sub     rsp, 40h
0x1400155a8  mov     edi, ecx
0x1400155aa  xor     ebx, ebx
0x1400155ac  mov     dword ptr [rax-28h], 1003h
0x1400155b3  mov     dword ptr [rax-24h], 1005h
0x1400155ba  mov     dword ptr [rax-20h], 1007h
0x1400155c1  mov     dword ptr [rax-1Ch], 1015h
0x1400155c8  mov     dword ptr [rax-18h], 1017h
0x1400155cf  movsxd  rcx, ebx
0x1400155d2  mov     r9d, 3; fWinIni
0x1400155d8  mov     r8, rdi; pvParam
0x1400155db  xor     edx, edx; uiParam
0x1400155dd  mov     ecx, [rsp+rcx*4+48h+uiAction]; uiAction
0x1400155e1  call    cs:__imp_SystemParametersInfoW
0x1400155e7  test    eax, eax
0x1400155e9  jz      short loc_14001561C
0x1400155eb  inc     ebx
0x1400155ed  cmp     ebx, 5
0x1400155f0  jb      short loc_1400155CF
0x1400155f2  xor     edx, edx; uiParam
0x1400155f4  mov     [rsp+48h+pvParam], 8
0x1400155fc  mov     r9d, 3; fWinIni
0x140015602  mov     [rsp+48h+arg_C], edi
0x140015606  lea     r8, [rsp+48h+pvParam]; pvParam
0x14001560b  lea     ecx, [rdx+49h]; uiAction
0x14001560e  call    cs:__imp_SystemParametersInfoW
0x140015614  test    eax, eax
0x140015616  jz      short loc_14001561C
0x140015618  xor     eax, eax
0x14001561a  jmp     short loc_14001562E
0x14001561c  call    cs:__imp_GetLastError
0x140015622  test    eax, eax
0x140015624  jle     short loc_14001562E
0x140015626  movzx   eax, ax
0x140015629  or      eax, 80070000h
0x14001562e  mov     rbx, [rsp+48h+arg_0]
0x140015633  mov     rsi, [rsp+48h+arg_10]
0x140015638  add     rsp, 40h
0x14001563c  pop     rdi
0x14001563d  retn
```
