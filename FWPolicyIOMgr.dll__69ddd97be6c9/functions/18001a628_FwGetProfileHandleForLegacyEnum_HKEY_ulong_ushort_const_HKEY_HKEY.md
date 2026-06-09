# FwGetProfileHandleForLegacyEnum(HKEY__ *,ulong,ushort const *,HKEY__ * *,HKEY__ * *)

- ea: `0x18001a628`
- end: `0x18001a70f`
- name: `?FwGetProfileHandleForLegacyEnum@@YAJPEAUHKEY__@@KPEBGPEAPEAU1@2@Z`
- size: `231`
- prototype: `__int64 __fastcall(HKEY, int, const unsigned __int16 *, HKEY *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ba5c`

## callees

- `0x1800042c4`
- `0x18001a628`
- `0x18001f650`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x18001a684`
- `fwbase!FwRegOpenKey` at `0x18001a684`

## pseudocode

```c
__int64 __fastcall FwGetProfileHandleForLegacyEnum(HKEY a1, int a2, const unsigned __int16 *a3, HKEY *a4, HKEY *a5)
{
  __int64 v5; // rax
  unsigned int v6; // ebx
  HKEY *v7; // rdi
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  int v11; // [rsp+30h] [rbp-28h] BYREF

  v11 = 0;
  if ( a2 == 1 )
  {
    v5 = 0;
    goto LABEL_5;
  }
  if ( (a2 & 2) != 0 )
  {
    v5 = 1;
LABEL_5:
    v6 = 0;
    v7 = &a4[v5];
    if ( !a4[v5] )
    {
      v6 = FwRegOpenKey(a1, a3, 9, v7, &v11);
      if ( (v6 & 0x80000000) != 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v9 = 66;
LABEL_15:
          WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v6);
          return v6;
        }
        return v6;
      }
      v6 &= -(v11 != 0);
    }
    *a5 = *v7;
    return v6;
  }
  v6 = -2147024894;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v9 = 65;
    goto LABEL_15;
  }
  return v6;
}

```

## disassembly

```asm
0x18001a628  push    rbx
0x18001a62a  push    rsi
0x18001a62b  push    rdi
0x18001a62c  sub     rsp, 40h
0x18001a630  mov     rax, cs:__security_cookie
0x18001a637  xor     rax, rsp
0x18001a63a  mov     [rsp+58h+var_20], rax
0x18001a63f  mov     rsi, [rsp+58h+arg_20]
0x18001a647  mov     r10, r8
0x18001a64a  mov     [rsp+58h+var_28], 0
0x18001a652  cmp     edx, 1
0x18001a655  jnz     short loc_18001A65B
0x18001a657  xor     eax, eax
0x18001a659  jmp     short loc_18001A665
0x18001a65b  test    dl, 2
0x18001a65e  jz      short loc_18001A6C2
0x18001a660  mov     eax, 8
0x18001a665  xor     ebx, ebx
0x18001a667  lea     rdi, [rax+r9]
0x18001a66b  cmp     [rdi], rbx
0x18001a66e  jnz     short loc_18001A6BA
0x18001a670  lea     rax, [rsp+58h+var_28]
0x18001a675  mov     r9, rdi
0x18001a678  lea     r8d, [rbx+9]
0x18001a67c  mov     [rsp+58h+var_38], rax
0x18001a681  mov     rdx, r10
0x18001a684  call    cs:__imp_FwRegOpenKey
0x18001a68a  mov     ebx, eax
0x18001a68c  test    eax, eax
0x18001a68e  jns     short loc_18001A6B0
0x18001a690  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a697  lea     rax, WPP_GLOBAL_Control
0x18001a69e  cmp     rcx, rax
0x18001a6a1  jz      short loc_18001A6F8
0x18001a6a3  test    byte ptr [rcx+1Ch], 1
0x18001a6a7  jz      short loc_18001A6F8
0x18001a6a9  mov     edx, 42h ; 'B'
0x18001a6ae  jmp     short loc_18001A6E5
0x18001a6b0  mov     eax, [rsp+58h+var_28]
0x18001a6b4  neg     eax
0x18001a6b6  sbb     ecx, ecx
0x18001a6b8  and     ebx, ecx
0x18001a6ba  mov     rax, [rdi]
0x18001a6bd  mov     [rsi], rax
0x18001a6c0  jmp     short loc_18001A6F8
0x18001a6c2  mov     ebx, 80070002h
0x18001a6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6ce  lea     rax, WPP_GLOBAL_Control
0x18001a6d5  cmp     rcx, rax
0x18001a6d8  jz      short loc_18001A6F8
0x18001a6da  test    byte ptr [rcx+1Ch], 1
0x18001a6de  jz      short loc_18001A6F8
0x18001a6e0  mov     edx, 41h ; 'A'
0x18001a6e5  mov     rcx, [rcx+10h]
0x18001a6e9  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001a6f0  mov     r9d, ebx
0x18001a6f3  call    WPP_SF_d
0x18001a6f8  mov     eax, ebx
0x18001a6fa  mov     rcx, [rsp+58h+var_20]
0x18001a6ff  xor     rcx, rsp; StackCookie
0x18001a702  call    __security_check_cookie
0x18001a707  add     rsp, 40h
0x18001a70b  pop     rdi
0x18001a70c  pop     rsi
0x18001a70d  pop     rbx
0x18001a70e  retn
```
