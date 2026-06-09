# WxGetPersistedRegistryLocation

- ea: `0x180013c84`
- end: `0x180013e39`
- name: `WxGetPersistedRegistryLocation`
- size: `437`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f670`

## callees

- `0x1800014b0`
- `0x180013c84`
- `0x180013e40`
- `0x180015008`
- `0x1800170b8`
- `0x1800171d4`
- `0x1800172d4`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180013cf9`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013cf9`

## pseudocode

```c
__int64 __fastcall WxGetPersistedRegistryLocation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int PersistedStateLocation; // eax
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // ebx
  unsigned int v13; // ebx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  _WORD *v16; // r9
  _WORD *v17; // r8
  _WORD *v18; // rcx
  unsigned int v20; // [rsp+40h] [rbp-48h] BYREF

  v20 = 0;
  if ( (BYTE3(xmmword_18001F260) & 0x20) != 0 )
    WPP_SF_SSSqd(a1, a2, a3, a1, a2, a3, a4);
  PersistedStateLocation = RtlGetPersistedStateLocation(a1, 0, a2, 0, a4, 522, &v20);
  v12 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_18001F260) & 0x20) != 0 )
      WPP_SF_SSSd(v10, v9, v11, a1, a2, a3, PersistedStateLocation);
    v13 = HRESULT_FROM_NTSTATUS(v12);
    goto LABEL_21;
  }
  v13 = 0;
  if ( a3 )
  {
    *(_WORD *)(a4 + 2 * ((unsigned __int64)v20 >> 1) - 2) = 92;
    v14 = (unsigned __int64)(522 - v20) >> 1;
    if ( v14 )
    {
      v15 = 2147483646;
      v16 = (_WORD *)a3;
      v17 = (_WORD *)(a4 + 2 * ((unsigned __int64)v20 >> 1));
      do
      {
        if ( !v15 )
          break;
        if ( !*v16 )
          break;
        *v17++ = *v16++;
        --v15;
        --v14;
      }
      while ( v14 );
      v18 = v17 - 1;
      if ( v14 )
        v18 = v17;
      *v18 = 0;
      v13 = v14 == 0 ? 0x8007007A : 0;
      if ( v14 )
      {
        if ( (BYTE3(xmmword_18001F260) & 0x20) == 0 )
          return v13;
        WPP_SF_SSSS((_DWORD)v18, v14, (_DWORD)v17, a1, a2, a3, a4);
        goto LABEL_21;
      }
    }
    else
    {
      v13 = -2147024809;
    }
    if ( (BYTE3(xmmword_18001F260) & 0x20) == 0 )
      return v13;
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v13);
  }
LABEL_21:
  if ( (BYTE3(xmmword_18001F260) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180013c84  mov     r11, rsp
0x180013c87  push    rbx
0x180013c88  push    rbp
0x180013c89  push    rsi
0x180013c8a  push    rdi
0x180013c8b  push    r12
0x180013c8d  push    r14
0x180013c8f  push    r15
0x180013c91  sub     rsp, 50h
0x180013c95  mov     rax, cs:__security_cookie
0x180013c9c  xor     rax, rsp
0x180013c9f  mov     [rsp+88h+var_40], rax
0x180013ca4  xor     r12d, r12d
0x180013ca7  mov     rsi, r9
0x180013caa  mov     [r11-48h], r12d
0x180013cae  mov     rdi, r8
0x180013cb1  mov     r14, rdx
0x180013cb4  mov     rbp, rcx
0x180013cb7  test    byte ptr cs:xmmword_18001F260+3, 20h
0x180013cbe  jz      short loc_180013CD4
0x180013cc0  mov     [r11-58h], r9
0x180013cc4  mov     r9, rcx
0x180013cc7  mov     [r11-60h], r8
0x180013ccb  mov     [r11-68h], rdx
0x180013ccf  call    WPP_SF_SSSqd
0x180013cd4  lea     rax, [rsp+88h+var_48]
0x180013cd9  mov     r15d, 20Ah
0x180013cdf  mov     [rsp+88h+var_58], rax
0x180013ce4  xor     r9d, r9d
0x180013ce7  mov     dword ptr [rsp+88h+var_60], r15d
0x180013cec  mov     r8, r14
0x180013cef  xor     edx, edx
0x180013cf1  mov     [rsp+88h+var_68], rsi
0x180013cf6  mov     rcx, rbp
0x180013cf9  call    cs:__imp_RtlGetPersistedStateLocation
0x180013cff  mov     ebx, eax
0x180013d01  test    eax, eax
0x180013d03  jns     short loc_180013D32
0x180013d05  test    byte ptr cs:xmmword_18001F260+3, 20h
0x180013d0c  jz      short loc_180013D24
0x180013d0e  mov     dword ptr [rsp+88h+var_58], eax
0x180013d12  mov     r9, rbp
0x180013d15  mov     [rsp+88h+var_60], rdi
0x180013d1a  mov     [rsp+88h+var_68], r14
0x180013d1f  call    WPP_SF_SSSd
0x180013d24  mov     ecx, ebx; int
0x180013d26  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180013d2b  mov     ebx, eax
0x180013d2d  jmp     loc_180013DF9
0x180013d32  mov     ebx, r12d
0x180013d35  test    rdi, rdi
0x180013d38  jz      loc_180013DF9
0x180013d3e  mov     eax, [rsp+88h+var_48]
0x180013d42  shr     rax, 1
0x180013d45  mov     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x180013d4c  sub     r15d, [rsp+88h+var_48]
0x180013d51  mov     edx, r15d
0x180013d54  shr     rdx, 1
0x180013d57  jz      short loc_180013DD2
0x180013d59  mov     eax, [rsp+88h+var_48]
0x180013d5d  mov     ecx, 7FFFFFFEh
0x180013d62  shr     rax, 1
0x180013d65  mov     r9, rdi
0x180013d68  lea     r8, [rsi+rax*2]
0x180013d6c  test    rcx, rcx
0x180013d6f  jz      short loc_180013D8F
0x180013d71  movzx   eax, word ptr [r9]
0x180013d75  test    ax, ax
0x180013d78  jz      short loc_180013D8F
0x180013d7a  mov     [r8], ax
0x180013d7e  add     r9, 2
0x180013d82  add     r8, 2
0x180013d86  dec     rcx
0x180013d89  sub     rdx, 1
0x180013d8d  jnz     short loc_180013D6C
0x180013d8f  mov     rax, rdx
0x180013d92  lea     rcx, [r8-2]
0x180013d96  neg     rax
0x180013d99  sbb     ebx, ebx
0x180013d9b  test    rdx, rdx
0x180013d9e  not     ebx
0x180013da0  cmovnz  rcx, r8
0x180013da4  mov     [rcx], r12w
0x180013da8  and     ebx, 8007007Ah
0x180013dae  js      short loc_180013DD7
0x180013db0  test    byte ptr cs:xmmword_18001F260+3, 20h
0x180013db7  jz      short loc_180013E1B
0x180013db9  mov     [rsp+88h+var_58], rsi
0x180013dbe  mov     r9, rbp
0x180013dc1  mov     [rsp+88h+var_60], rdi
0x180013dc6  mov     [rsp+88h+var_68], r14
0x180013dcb  call    WPP_SF_SSSS
0x180013dd0  jmp     short loc_180013DF9
0x180013dd2  mov     ebx, 80070057h
0x180013dd7  mov     r9d, ebx
0x180013dda  test    byte ptr cs:xmmword_18001F260+3, 20h
0x180013de1  jz      short loc_180013E1B
0x180013de3  mov     edx, 0Ch
0x180013de8  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180013def  mov     ecx, 41Dh
0x180013df4  call    WPP_SF_d
0x180013df9  test    byte ptr cs:xmmword_18001F260+3, 20h
0x180013e00  jz      short loc_180013E1B
0x180013e02  mov     edx, 0Eh
0x180013e07  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180013e0e  mov     ecx, 41Dh
0x180013e13  mov     r9d, ebx
0x180013e16  call    WPP_SF_d
0x180013e1b  mov     eax, ebx
0x180013e1d  mov     rcx, [rsp+88h+var_40]
0x180013e22  xor     rcx, rsp; StackCookie
0x180013e25  call    __security_check_cookie
0x180013e2a  add     rsp, 50h
0x180013e2e  pop     r15
0x180013e30  pop     r14
0x180013e32  pop     r12
0x180013e34  pop     rdi
0x180013e35  pop     rsi
0x180013e36  pop     rbp
0x180013e37  pop     rbx
0x180013e38  retn
```
