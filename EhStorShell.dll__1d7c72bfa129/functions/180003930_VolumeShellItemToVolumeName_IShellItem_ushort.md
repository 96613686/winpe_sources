# VolumeShellItemToVolumeName(IShellItem *,ushort * *)

- ea: `0x180003930`
- end: `0x180003a8f`
- name: `?VolumeShellItemToVolumeName@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003670`
- `0x18000adb4`

## callees

- `0x180003930`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003a6e`
- `ole32!CoTaskMemFree` at `0x180003a6e`
- `SHLWAPI!SHStrDupW` at `0x180003a54`
- `SHLWAPI!SHStrDupW` at `0x180003a54`

## pseudocode

```c
__int64 __fastcall VolumeShellItemToVolumeName(struct IShellItem *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  void *v4; // rdx
  __int64 v5; // rcx
  _WORD *v6; // rax
  __int64 v7; // rax
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // r9
  WCHAR v11; // r10
  WCHAR *v12; // rcx
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  WCHAR psz[2]; // [rsp+28h] [rbp-18h] BYREF
  WCHAR v16; // [rsp+30h] [rbp-10h]
  WCHAR v17; // [rsp+32h] [rbp-Eh]
  __int16 v18; // [rsp+34h] [rbp-Ch]

  pv = 0;
  v3 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a1->lpVtbl->GetDisplayName)(
         a1,
         2147844096LL,
         &pv);
  v4 = pv;
  if ( v3 >= 0 )
  {
    if ( pv )
    {
      v5 = 0x7FFFFFFF;
      v6 = pv;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      v3 = -2147024809;
      if ( v5 )
      {
        if ( ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) == 3 )
        {
          v7 = 2147483646;
          v8 = (WCHAR *)pv;
          v9 = 7;
          v10 = psz;
          do
          {
            if ( !v7 )
              break;
            v11 = *v8;
            if ( !*v8 )
              break;
            ++v8;
            *v10++ = v11;
            --v7;
            --v9;
          }
          while ( v9 );
          v3 = v9 == 0 ? 0x8007007A : 0;
          v12 = v10 - 1;
          if ( v9 )
            v12 = v10;
          *v12 = 0;
          if ( v9 )
          {
            v16 = psz[0];
            v17 = psz[1];
            v18 = 0;
            wmemcpy(psz, L"\\\\.\\", 4);
            v3 = SHStrDupW(psz, a2);
            v4 = pv;
          }
        }
      }
      else
      {
        v3 = -2147024809;
      }
    }
    else
    {
      v3 = -2147024809;
    }
  }
  pv = 0;
  CoTaskMemFree(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003930  mov     [rsp-18h+arg_10], rbx
0x180003935  push    rbp
0x180003936  push    rsi
0x180003937  push    rdi
0x180003938  mov     rbp, rsp
0x18000393b  sub     rsp, 40h
0x18000393f  mov     rax, cs:__security_cookie
0x180003946  xor     rax, rsp
0x180003949  mov     [rbp+var_8], rax
0x18000394d  mov     rdi, rdx
0x180003950  xor     esi, esi
0x180003952  mov     [rbp+pv], rsi
0x180003956  mov     rax, [rcx]
0x180003959  lea     r8, [rbp+pv]
0x18000395d  mov     edx, 80058000h
0x180003962  mov     rax, [rax+28h]
0x180003966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000396b  mov     ebx, eax
0x18000396d  mov     rdx, [rbp+pv]
0x180003971  test    eax, eax
0x180003973  js      loc_180003A67
0x180003979  test    rdx, rdx
0x18000397c  jz      loc_180003A62
0x180003982  mov     r9d, 7FFFFFFFh
0x180003988  mov     ecx, r9d
0x18000398b  mov     rax, rdx
0x18000398e  cmp     [rax], si
0x180003991  jz      short loc_18000399D
0x180003993  add     rax, 2
0x180003997  sub     rcx, 1
0x18000399b  jnz     short loc_18000398E
0x18000399d  mov     rax, rcx
0x1800039a0  neg     rax
0x1800039a3  sbb     r8d, r8d
0x1800039a6  not     r8d
0x1800039a9  mov     ebx, 80070057h
0x1800039ae  and     r8d, ebx
0x1800039b1  mov     rax, rcx
0x1800039b4  sub     r9, rcx
0x1800039b7  neg     rax
0x1800039ba  sbb     r10, r10
0x1800039bd  and     r10, r9
0x1800039c0  test    rcx, rcx
0x1800039c3  jnz     short loc_1800039CD
0x1800039c5  mov     ebx, r8d
0x1800039c8  jmp     loc_180003A67
0x1800039cd  cmp     r10, 3
0x1800039d1  jnz     loc_180003A67
0x1800039d7  mov     eax, 7FFFFFFEh
0x1800039dc  mov     rcx, rdx
0x1800039df  lea     r8d, [r10+4]
0x1800039e3  lea     r9, [rbp+psz]
0x1800039e7  test    rax, rax
0x1800039ea  jz      short loc_180003A0B
0x1800039ec  movzx   r10d, word ptr [rcx]
0x1800039f0  test    r10w, r10w
0x1800039f4  jz      short loc_180003A0B
0x1800039f6  add     rcx, 2
0x1800039fa  mov     [r9], r10w
0x1800039fe  add     r9, 2
0x180003a02  dec     rax
0x180003a05  sub     r8, 1
0x180003a09  jnz     short loc_1800039E7
0x180003a0b  mov     rax, r8
0x180003a0e  neg     rax
0x180003a11  sbb     ebx, ebx
0x180003a13  not     ebx
0x180003a15  and     ebx, 8007007Ah
0x180003a1b  lea     rcx, [r9-2]
0x180003a1f  test    r8, r8
0x180003a22  cmovnz  rcx, r9
0x180003a26  mov     [rcx], si
0x180003a29  jz      short loc_180003A67
0x180003a2b  movzx   eax, [rbp+psz]
0x180003a2f  mov     [rbp+var_10], ax
0x180003a33  movzx   eax, [rbp+psz+2]
0x180003a37  mov     [rbp+var_E], ax
0x180003a3b  mov     [rbp+var_C], si
0x180003a3f  mov     dword ptr [rbp+psz], 5C005Ch
0x180003a46  mov     [rbp+var_14], 5C002Eh
0x180003a4d  mov     rdx, rdi; ppwsz
0x180003a50  lea     rcx, [rbp+psz]; psz
0x180003a54  call    cs:__imp_SHStrDupW
0x180003a5a  mov     ebx, eax
0x180003a5c  mov     rdx, [rbp+pv]
0x180003a60  jmp     short loc_180003A67
0x180003a62  mov     ebx, 80070057h
0x180003a67  mov     [rbp+pv], rsi
0x180003a6b  mov     rcx, rdx; pv
0x180003a6e  call    cs:__imp_CoTaskMemFree
0x180003a74  mov     eax, ebx
0x180003a76  mov     rcx, [rbp+var_8]
0x180003a7a  xor     rcx, rsp; StackCookie
0x180003a7d  call    __security_check_cookie
0x180003a82  mov     rbx, [rsp+40h+arg_10]
0x180003a87  add     rsp, 40h
0x180003a8b  pop     rdi
0x180003a8c  pop     rsi
0x180003a8d  pop     rbp
0x180003a8e  retn
```
