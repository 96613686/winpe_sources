# ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)

- ea: `0x140007708`
- end: `0x140007799`
- name: `?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z`
- size: `145`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, BYTE *, unsigned int *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f00`
- `0x14000ddb0`
- `0x14000df88`
- `0x14000e0c0`
- `0x14000e3e8`
- `0x14000e538`
- `0x14000ee8c`
- `0x140011a40`

## callees

- `0x140007708`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140007746`
- `ADVAPI32!RegQueryValueExW` at `0x140007746`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::QueryStringValue(HKEY *this, const unsigned __int16 *a2, BYTE *a3, unsigned int *a4)
{
  unsigned int v5; // eax
  HKEY v7; // rcx
  LSTATUS result; // eax
  DWORD v9; // ecx
  DWORD v10; // [rsp+40h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+20h] BYREF

  v5 = 2 * *a4;
  *a4 = 0;
  v7 = *this;
  v11 = v5;
  v10 = 0;
  result = RegQueryValueExW(v7, a2, 0, &v10, a3, &v11);
  if ( !result )
  {
    if ( v10 - 1 <= 1 )
    {
      v9 = v11;
      if ( a3 )
      {
        if ( v11 )
        {
          if ( (v11 & 1) != 0 || *(_WORD *)&a3[2 * ((unsigned __int64)v11 >> 1) - 2] )
            return 13;
        }
        else
        {
          *(_WORD *)a3 = 0;
        }
      }
      *a4 = v9 >> 1;
      return 0;
    }
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x140007708  mov     r11, rsp
0x14000770b  mov     [r11+10h], rbx
0x14000770f  mov     [r11+18h], rsi
0x140007713  push    rdi
0x140007714  sub     rsp, 30h
0x140007718  mov     eax, [r9]
0x14000771b  mov     rbx, r8
0x14000771e  add     eax, eax
0x140007720  xor     esi, esi
0x140007722  mov     [r9], esi
0x140007725  mov     rdi, r9
0x140007728  mov     rcx, [rcx]; hKey
0x14000772b  lea     r9, [r11+8]; lpType
0x14000772f  mov     [rsp+38h+arg_18], eax
0x140007733  xor     r8d, r8d; lpReserved
0x140007736  lea     rax, [r11+20h]
0x14000773a  mov     [rsp+38h+arg_0], esi
0x14000773e  mov     [r11-10h], rax
0x140007742  mov     [r11-18h], rbx
0x140007746  call    cs:__imp_RegQueryValueExW
0x14000774c  test    eax, eax
0x14000774e  jnz     short loc_14000777E
0x140007750  mov     eax, [rsp+38h+arg_0]
0x140007754  dec     eax
0x140007756  cmp     eax, 1
0x140007759  ja      short loc_140007779
0x14000775b  mov     ecx, [rsp+38h+arg_18]
0x14000775f  test    rbx, rbx
0x140007762  jz      short loc_140007791
0x140007764  test    ecx, ecx
0x140007766  jz      short loc_14000778E
0x140007768  test    cl, 1
0x14000776b  jnz     short loc_140007779
0x14000776d  mov     eax, ecx
0x14000776f  shr     rax, 1
0x140007772  cmp     [rbx+rax*2-2], si
0x140007777  jz      short loc_140007791
0x140007779  mov     eax, 0Dh
0x14000777e  mov     rbx, [rsp+38h+arg_8]
0x140007783  mov     rsi, [rsp+38h+arg_10]
0x140007788  add     rsp, 30h
0x14000778c  pop     rdi
0x14000778d  retn
0x14000778e  mov     [rbx], si
0x140007791  shr     ecx, 1
0x140007793  mov     [rdi], ecx
0x140007795  xor     eax, eax
0x140007797  jmp     short loc_14000777E
```
