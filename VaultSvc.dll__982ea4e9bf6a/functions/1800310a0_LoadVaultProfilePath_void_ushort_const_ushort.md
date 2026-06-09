# LoadVaultProfilePath(void *,ushort const *,ushort * *)

- ea: `0x1800310a0`
- end: `0x1800311a0`
- name: `?LoadVaultProfilePath@@YAKPEAXPEBGPEAPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ff18`

## callees

- `0x180003140`
- `0x1800310a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031134`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031134`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800310ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800310ec`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18003110f`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18003110f`

## pseudocode

```c
__int64 __fastcall LoadVaultProfilePath(void *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v6; // esi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-50h]
  __int64 v14; // [rsp+30h] [rbp-48h]

  v13 = 0;
  LODWORD(v14) = 0;
  v12 = 0;
  v6 = 0;
  while ( 1 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
    v6 += 260;
    v7 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v6);
    v8 = v7;
    v13 = v7;
    if ( !v7 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
      return 14;
    }
    v9 = ExpandEnvStringForUser(a1, a2, v7, v6, v12, v13, v14);
    v10 = v9;
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    if ( !v10 )
      break;
    if ( v10 != 122 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
      return v10;
    }
  }
  if ( (unsigned int)_o__wcsicmp(v8, a2) )
  {
    v13 = 0;
    *a3 = v8;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
    return 0;
  }
  else
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
    return 2016;
  }
}

```

## disassembly

```asm
0x1800310a0  push    rbx
0x1800310a2  push    rbp
0x1800310a3  push    rsi
0x1800310a4  push    rdi
0x1800310a5  push    r14
0x1800310a7  push    r15
0x1800310a9  sub     rsp, 48h
0x1800310ad  mov     r14, r8
0x1800310b0  mov     rbp, rdx
0x1800310b3  mov     r15, rcx
0x1800310b6  mov     [rsp+78h+var_50], 0
0x1800310bf  mov     dword ptr [rsp+78h+var_48], 0
0x1800310c7  mov     [rsp+78h+var_58], 0
0x1800310d0  xor     esi, esi
0x1800310d2  lea     rcx, [rsp+78h+var_58]
0x1800310d7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800310dc  add     esi, 104h
0x1800310e2  mov     edx, esi
0x1800310e4  add     rdx, rdx; uBytes
0x1800310e7  mov     ecx, 40h ; '@'; uFlags
0x1800310ec  call    cs:__imp_LocalAlloc
0x1800310f2  mov     rdi, rax
0x1800310f5  mov     [rsp+78h+var_50], rax
0x1800310fa  test    rax, rax
0x1800310fd  jz      loc_18003118E
0x180031103  mov     r9d, esi
0x180031106  mov     r8, rax
0x180031109  mov     rdx, rbp
0x18003110c  mov     rcx, r15
0x18003110f  call    cs:__imp_ExpandEnvStringForUser
0x180031115  mov     ebx, eax
0x180031117  mov     ecx, eax
0x180031119  and     ecx, 1FFF0000h
0x18003111f  cmp     ecx, 70000h
0x180031125  jnz     short loc_18003112A
0x180031127  movzx   ebx, ax
0x18003112a  test    ebx, ebx
0x18003112c  jnz     short loc_180031164
0x18003112e  mov     rdx, rbp
0x180031131  mov     rcx, rdi
0x180031134  call    cs:__imp__o__wcsicmp
0x18003113a  test    eax, eax
0x18003113c  jz      short loc_18003117C
0x18003113e  mov     [rsp+78h+var_50], 0
0x180031147  mov     [r14], rdi
0x18003114a  lea     rcx, [rsp+78h+var_58]
0x18003114f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031154  nop
0x180031155  xor     eax, eax
0x180031157  add     rsp, 48h
0x18003115b  pop     r15
0x18003115d  pop     r14
0x18003115f  pop     rdi
0x180031160  pop     rsi
0x180031161  pop     rbp
0x180031162  pop     rbx
0x180031163  retn
0x180031164  cmp     ebx, 7Ah ; 'z'
0x180031167  jz      loc_1800310D2
0x18003116d  lea     rcx, [rsp+78h+var_58]
0x180031172  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031177  nop
0x180031178  mov     eax, ebx
0x18003117a  jmp     short loc_180031157
0x18003117c  lea     rcx, [rsp+78h+var_58]
0x180031181  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031186  nop
0x180031187  mov     eax, 7E0h
0x18003118c  jmp     short loc_180031157
0x18003118e  lea     rcx, [rsp+78h+var_58]
0x180031193  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031198  nop
0x180031199  mov     eax, 0Eh
0x18003119e  jmp     short loc_180031157
```
