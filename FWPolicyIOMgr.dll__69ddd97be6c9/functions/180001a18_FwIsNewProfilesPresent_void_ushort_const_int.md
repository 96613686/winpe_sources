# FwIsNewProfilesPresent(void *,ushort const * *,int *)

- ea: `0x180001a18`
- end: `0x180001b02`
- name: `?FwIsNewProfilesPresent@@YAJPEAXPEAPEBGPEAH@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002590`

## callees

- `0x180001a18`
- `0x1800042c4`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x180001a61`
- `fwbase!FwRegOpenKey` at `0x180001a88`
- `fwbase!FwRegOpenKey` at `0x180001a61`
- `fwbase!FwRegOpenKey` at `0x180001a88`

## pseudocode

```c
__int64 __fastcall FwIsNewProfilesPresent(_QWORD *a1, const unsigned __int16 **a2, int *a3)
{
  char *v6; // r14
  int v7; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx

  *a3 = 0;
  if ( a1[24] || (v6 = (char *)(a1 + 23), a1[23]) )
  {
    *a3 = 1;
    return 0;
  }
  else
  {
    v7 = FwRegOpenKey(a1[5], a2[3], 1, a1 + 24, a3);
    if ( v7 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 53;
LABEL_11:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v7);
      }
    }
    else if ( !*a3 )
    {
      v7 = FwRegOpenKey(a1[5], a2[2], 1, v6, a3);
      if ( v7 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 54;
          goto LABEL_11;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001a18  push    rbx
0x180001a1a  push    rbp
0x180001a1b  push    rsi
0x180001a1c  push    r14
0x180001a1e  push    r15
0x180001a20  sub     rsp, 30h
0x180001a24  lea     r9, [rcx+0C0h]
0x180001a2b  mov     dword ptr [r8], 0
0x180001a32  cmp     qword ptr [r9], 0
0x180001a36  mov     rsi, r8
0x180001a39  mov     r15, rdx
0x180001a3c  mov     rbp, rcx
0x180001a3f  jnz     short loc_180001AA2
0x180001a41  lea     r14, [rcx+0B8h]
0x180001a48  cmp     qword ptr [r14], 0
0x180001a4c  jnz     short loc_180001AA2
0x180001a4e  mov     rdx, [rdx+18h]
0x180001a52  mov     rcx, [rcx+28h]
0x180001a56  mov     [rsp+58h+var_38], r8
0x180001a5b  mov     r8d, 1
0x180001a61  call    cs:__imp_FwRegOpenKey
0x180001a67  mov     ebx, eax
0x180001a69  test    eax, eax
0x180001a6b  js      short loc_180001AAD
0x180001a6d  cmp     dword ptr [rsi], 0
0x180001a70  jnz     short loc_180001A94
0x180001a72  mov     rdx, [r15+10h]
0x180001a76  mov     r9, r14
0x180001a79  mov     rcx, [rbp+28h]
0x180001a7d  mov     r8d, 1
0x180001a83  mov     [rsp+58h+var_38], rsi
0x180001a88  call    cs:__imp_FwRegOpenKey
0x180001a8e  mov     ebx, eax
0x180001a90  test    eax, eax
0x180001a92  js      short loc_180001AE7
0x180001a94  mov     eax, ebx
0x180001a96  add     rsp, 30h
0x180001a9a  pop     r15
0x180001a9c  pop     r14
0x180001a9e  pop     rsi
0x180001a9f  pop     rbp
0x180001aa0  pop     rbx
0x180001aa1  retn
0x180001aa2  mov     dword ptr [r8], 1
0x180001aa9  xor     ebx, ebx
0x180001aab  jmp     short loc_180001A94
0x180001aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ab4  lea     rax, WPP_GLOBAL_Control
0x180001abb  cmp     rcx, rax
0x180001abe  jz      short loc_180001A94
0x180001ac0  test    byte ptr [rcx+1Ch], 1
0x180001ac4  jz      short loc_180001A94
0x180001ac6  mov     edx, 35h ; '5'
0x180001acb  jmp     short loc_180001AD2
0x180001acd  mov     edx, 36h ; '6'
0x180001ad2  mov     rcx, [rcx+10h]
0x180001ad6  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180001add  mov     r9d, ebx
0x180001ae0  call    WPP_SF_d
0x180001ae5  jmp     short loc_180001A94
0x180001ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180001aee  lea     rax, WPP_GLOBAL_Control
0x180001af5  cmp     rcx, rax
0x180001af8  jz      short loc_180001A94
0x180001afa  test    byte ptr [rcx+1Ch], 1
0x180001afe  jz      short loc_180001A94
0x180001b00  jmp     short loc_180001ACD
```
