# DelOEMRUString

- ea: `0x18000de50`
- end: `0x18000df41`
- name: `DelOEMRUString`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180004640`
- `0x18000de50`
- `0x180012d14`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000df1c`
- `ADVAPI32!RegSetValueExW` at `0x18000df1c`

## pseudocode

```c
__int64 __fastcall DelOEMRUString(__int64 a1, int a2)
{
  unsigned int v3; // ebp
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned __int16 *v7; // rsi
  unsigned __int64 v8; // rdx
  const BYTE *lpData; // rcx

  v3 = 0;
  if ( !a1 )
    return v3;
  if ( a2 >= 0 && a2 < *(_DWORD *)(a1 + 4) )
  {
    v4 = *(_QWORD *)(a1 + 24);
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v4 + 2 * v6) );
    if ( a2 < (int)v6 )
    {
      v7 = (unsigned __int16 *)(v4 + 2LL * a2);
      if ( v7 )
      {
        if ( (unsigned __int16)(*v7 - 97) <= 0x1Cu )
          Str_SetPtrW((LPWSTR *)(a1 + 8 * (*v7 - 93LL)), 0);
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
        StringCchCopyW(v7, v8, v7 + 1);
        v3 = 1;
        if ( (*(_DWORD *)a1 & 2) != 0 )
        {
          *(_DWORD *)a1 |= 0x1000u;
        }
        else
        {
          lpData = *(const BYTE **)(a1 + 24);
          do
            ++v5;
          while ( *(_WORD *)&lpData[2 * v5] );
          RegSetValueExW(*(HKEY *)(a1 + 16), L"MRUList", 0, 1u, lpData, 2 * v5 + 2);
          *(_DWORD *)a1 &= ~0x1000u;
        }
      }
      return v3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000de50  push    rbx
0x18000de52  push    rbp
0x18000de53  push    rsi
0x18000de54  push    rdi
0x18000de55  push    r14
0x18000de57  sub     rsp, 30h
0x18000de5b  xor     r14d, r14d
0x18000de5e  mov     rbx, rcx
0x18000de61  mov     ebp, r14d
0x18000de64  test    rcx, rcx
0x18000de67  jz      loc_18000DF26
0x18000de6d  test    edx, edx
0x18000de6f  js      loc_18000DF3D
0x18000de75  cmp     edx, [rcx+4]
0x18000de78  jge     loc_18000DF3D
0x18000de7e  mov     rcx, [rcx+18h]
0x18000de82  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000de86  mov     rax, rdi
0x18000de89  inc     rax
0x18000de8c  cmp     [rcx+rax*2], r14w
0x18000de91  jnz     short loc_18000DE89
0x18000de93  cmp     edx, eax
0x18000de95  jge     loc_18000DF3D
0x18000de9b  movsxd  rax, edx
0x18000de9e  lea     rsi, [rcx+rax*2]
0x18000dea2  test    rsi, rsi
0x18000dea5  jz      short loc_18000DF26
0x18000dea7  movzx   eax, word ptr [rsi]
0x18000deaa  sub     ax, 61h ; 'a'
0x18000deae  cmp     ax, 1Ch
0x18000deb2  ja      short loc_18000DEC6
0x18000deb4  movzx   eax, word ptr [rsi]
0x18000deb7  xor     edx, edx; psz
0x18000deb9  add     rax, 0FFFFFFFFFFFFFFA3h
0x18000debd  lea     rcx, [rbx+rax*8]; ppsz
0x18000dec1  call    Str_SetPtrW
0x18000dec6  mov     rdx, rdi
0x18000dec9  inc     rdx; unsigned __int64
0x18000decc  cmp     [rsi+rdx*2], r14w
0x18000ded1  jnz     short loc_18000DEC9
0x18000ded3  lea     r8, [rsi+2]; unsigned __int16 *
0x18000ded7  mov     rcx, rsi; unsigned __int16 *
0x18000deda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dedf  mov     r11d, [rbx]
0x18000dee2  mov     ebp, 1
0x18000dee7  test    r11b, 2
0x18000deeb  jnz     short loc_18000DF33
0x18000deed  mov     rcx, [rbx+18h]
0x18000def1  inc     rdi
0x18000def4  cmp     [rcx+rdi*2], r14w
0x18000def9  jnz     short loc_18000DEF1
0x18000defb  lea     eax, ds:2[rdi*2]
0x18000df02  mov     r9d, ebp; dwType
0x18000df05  mov     [rsp+58h+cbData], eax; cbData
0x18000df09  lea     rdx, aMrulist; "MRUList"
0x18000df10  mov     [rsp+58h+lpData], rcx; lpData
0x18000df15  xor     r8d, r8d; Reserved
0x18000df18  mov     rcx, [rbx+10h]; hKey
0x18000df1c  call    cs:__imp_RegSetValueExW
0x18000df22  btr     dword ptr [rbx], 0Ch
0x18000df26  mov     eax, ebp
0x18000df28  add     rsp, 30h
0x18000df2c  pop     r14
0x18000df2e  pop     rdi
0x18000df2f  pop     rsi
0x18000df30  pop     rbp
0x18000df31  pop     rbx
0x18000df32  retn
0x18000df33  bts     r11d, 0Ch
0x18000df38  mov     [rbx], r11d
0x18000df3b  jmp     short loc_18000DF26
0x18000df3d  xor     eax, eax
0x18000df3f  jmp     short loc_18000DF28
```
