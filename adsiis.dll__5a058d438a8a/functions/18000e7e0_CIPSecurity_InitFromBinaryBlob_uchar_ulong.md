# CIPSecurity::InitFromBinaryBlob(uchar *,ulong)

- ea: `0x18000e7e0`
- end: `0x18000e9e2`
- name: `?InitFromBinaryBlob@CIPSecurity@@QEAAJPEAEK@Z`
- size: `514`
- prototype: `int(CIPSecurity *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180018518`

## callees

- `0x18000e7e0`
- `0x18001cb90`
- `0x18001cce0`
- `0x18001ce84`
- `0x18001cfcc`
- `0x18001d652`
- `0x18001d66a`
- `0x18001d676`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e992`
- `msvcrt!sprintf_s` at `0x18000e992`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e815`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e815`

## pseudocode

```c
__int64 __fastcall CIPSecurity::InitFromBinaryBlob(CIPSecurity *this, unsigned __int8 *a2, DWORD a3)
{
  size_t v3; // rbx
  unsigned __int8 *v6; // rax
  unsigned __int8 *v7; // rdi
  ADDRESS_CHECK *v9; // rcx
  unsigned int NbName; // eax
  __int64 v11; // r9
  int v12; // r10d
  unsigned int v13; // r11d
  int v14; // ecx
  unsigned int v15; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int8 *v16; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int8 *v17; // [rsp+70h] [rbp-98h] BYREF
  char Buffer[80]; // [rsp+80h] [rbp-88h] BYREF

  v3 = a3;
  if ( a2 && a3 )
  {
    v6 = (unsigned __int8 *)AllocADsMem(a3);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    memcpy_0(v6, a2, v3);
  }
  else
  {
    v7 = 0;
    LODWORD(v3) = 0;
  }
  ADDRESS_CHECK::BindCheckList((CIPSecurity *)((char *)this + 24), v7, v3);
  ADDRESS_CHECK::GetNbName((CIPSecurity *)((char *)this + 24), 0);
  NbName = ADDRESS_CHECK::GetNbName(v9, 1);
  if ( NbName + v12 <= v13 )
  {
    *((_DWORD *)this + 58) = 1;
  }
  else
  {
    *((_DWORD *)this + 58) = 0;
    if ( NbName + v12 == 1 )
    {
      v14 = v11 ? *(_DWORD *)((*(_DWORD *)(v11 + 4) & 0x7FFFFFFF) + v11 + 4) : 0;
      if ( v14 == 1 )
      {
        v15 = 0;
        v16 = 0;
        v17 = 0;
        memset_0(Buffer, 0, sizeof(Buffer));
        if ( (unsigned int)ADDRESS_CHECK::GetAddr((CIPSecurity *)((char *)this + 24), 1, 0, &v15, &v16, &v17) == 1 )
          sprintf_s(
            Buffer,
            0x50u,
            "%d.%d.%d.%d, %d.%d.%d.%d",
            v17[3],
            v17[2],
            v17[1],
            *v17,
            v16[3],
            v16[2],
            v16[1],
            *v16);
        if ( !strcmp_0(Buffer, "0.0.0.0, 255.255.255.255") )
          ADDRESS_CHECK::DeleteAllAddr((CIPSecurity *)((char *)this + 24), 1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e7e0  push    rbx
0x18000e7e2  push    rbp
0x18000e7e3  push    rsi
0x18000e7e4  push    rdi
0x18000e7e5  push    r14
0x18000e7e7  sub     rsp, 0E0h
0x18000e7ee  mov     rax, cs:__security_cookie
0x18000e7f5  xor     rax, rsp
0x18000e7f8  mov     [rsp+108h+var_38], rax
0x18000e800  mov     ebx, r8d
0x18000e803  mov     rbp, rdx
0x18000e806  mov     rsi, rcx
0x18000e809  test    rdx, rdx
0x18000e80c  jz      short loc_18000E83D
0x18000e80e  test    r8d, r8d
0x18000e811  jz      short loc_18000E83D
0x18000e813  mov     ecx, ebx; cb
0x18000e815  call    cs:__imp_AllocADsMem
0x18000e81b  mov     rdi, rax
0x18000e81e  test    rax, rax
0x18000e821  jnz     short loc_18000E82D
0x18000e823  mov     eax, 8007000Eh
0x18000e828  jmp     loc_18000E9C4
0x18000e82d  mov     r8, rbx; Size
0x18000e830  mov     rdx, rbp; Src
0x18000e833  mov     rcx, rax; void *
0x18000e836  call    memcpy_0
0x18000e83b  jmp     short loc_18000E841
0x18000e83d  xor     edi, edi
0x18000e83f  xor     ebx, ebx
0x18000e841  lea     r14, [rsi+18h]
0x18000e845  mov     r8d, ebx; unsigned int
0x18000e848  mov     rcx, r14; this
0x18000e84b  mov     rdx, rdi; unsigned __int8 *
0x18000e84e  call    ?BindCheckList@ADDRESS_CHECK@@QEAAHPEAEK@Z; ADDRESS_CHECK::BindCheckList(uchar *,ulong)
0x18000e853  mov     r9, [r14]
0x18000e856  mov     ebx, 7FFFFFFFh
0x18000e85b  test    r9, r9
0x18000e85e  jz      short loc_18000E86D
0x18000e860  mov     eax, [r9]
0x18000e863  and     rax, rbx
0x18000e866  mov     r10d, [rax+r9+4]
0x18000e86b  jmp     short loc_18000E870
0x18000e86d  xor     r10d, r10d
0x18000e870  xor     edx, edx; int
0x18000e872  mov     rcx, r14; this
0x18000e875  call    ?GetNbName@ADDRESS_CHECK@@QEAAKH@Z; ADDRESS_CHECK::GetNbName(int)
0x18000e87a  lea     r11d, [rax+r10]
0x18000e87e  test    r9, r9
0x18000e881  jz      short loc_18000E891
0x18000e883  mov     eax, [r9+4]
0x18000e887  and     rax, rbx
0x18000e88a  mov     r10d, [rax+r9+4]
0x18000e88f  jmp     short loc_18000E894
0x18000e891  xor     r10d, r10d
0x18000e894  mov     ebp, 1
0x18000e899  mov     edx, ebp; int
0x18000e89b  call    ?GetNbName@ADDRESS_CHECK@@QEAAKH@Z; ADDRESS_CHECK::GetNbName(int)
0x18000e8a0  lea     ecx, [rax+r10]
0x18000e8a4  cmp     ecx, r11d
0x18000e8a7  jbe     loc_18000E9BC
0x18000e8ad  mov     dword ptr [rsi+0E8h], 0
0x18000e8b7  cmp     ecx, ebp
0x18000e8b9  jnz     loc_18000E9C2
0x18000e8bf  test    r9, r9
0x18000e8c2  jz      short loc_18000E8D2
0x18000e8c4  mov     eax, [r9+4]
0x18000e8c8  and     rax, rbx
0x18000e8cb  mov     ecx, [rax+r9+4]
0x18000e8d0  jmp     short loc_18000E8D4
0x18000e8d2  xor     ecx, ecx
0x18000e8d4  cmp     ecx, ebp
0x18000e8d6  jnz     loc_18000E9C2
0x18000e8dc  xor     edx, edx; Val
0x18000e8de  mov     [rsp+108h+var_A8], 0
0x18000e8e6  lea     rcx, [rsp+108h+Buffer]; void *
0x18000e8ee  mov     [rsp+108h+var_A0], 0
0x18000e8f7  mov     [rsp+108h+var_98], 0
0x18000e900  lea     r8d, [rdx+50h]; Size
0x18000e904  call    memset_0
0x18000e909  lea     rax, [rsp+108h+var_98]
0x18000e90e  xor     r8d, r8d; unsigned int
0x18000e911  mov     [rsp+108h+var_E0], rax; unsigned __int8 **
0x18000e916  lea     r9, [rsp+108h+var_A8]; unsigned int *
0x18000e91b  lea     rax, [rsp+108h+var_A0]
0x18000e920  mov     edx, ebp; int
0x18000e922  mov     rcx, r14; this
0x18000e925  mov     [rsp+108h+var_E8], rax; unsigned __int8 **
0x18000e92a  call    ?GetAddr@ADDRESS_CHECK@@QEAAHHKPEAKPEAPEAE1@Z; ADDRESS_CHECK::GetAddr(int,ulong,ulong *,uchar * *,uchar * *)
0x18000e92f  cmp     eax, ebp
0x18000e931  jnz     short loc_18000E998
0x18000e933  mov     rax, [rsp+108h+var_A0]
0x18000e938  mov     edx, 50h ; 'P'; BufferCount
0x18000e93d  movzx   r11d, byte ptr [rax]
0x18000e941  movzx   ebx, byte ptr [rax+1]
0x18000e945  movzx   edi, byte ptr [rax+2]
0x18000e949  movzx   esi, byte ptr [rax+3]
0x18000e94d  mov     rax, [rsp+108h+var_98]
0x18000e952  mov     [rsp+108h+var_B8], r11d
0x18000e957  mov     [rsp+108h+var_C0], ebx
0x18000e95b  mov     [rsp+108h+var_C8], edi
0x18000e95f  movzx   ecx, byte ptr [rax]
0x18000e962  movzx   r8d, byte ptr [rax+1]
0x18000e967  movzx   r10d, byte ptr [rax+2]
0x18000e96c  movzx   r9d, byte ptr [rax+3]
0x18000e971  mov     [rsp+108h+var_D0], esi
0x18000e975  mov     [rsp+108h+var_D8], ecx
0x18000e979  lea     rcx, [rsp+108h+Buffer]; Buffer
0x18000e981  mov     dword ptr [rsp+108h+var_E0], r8d
0x18000e986  lea     r8, Format; "%d.%d.%d.%d, %d.%d.%d.%d"
0x18000e98d  mov     dword ptr [rsp+108h+var_E8], r10d
0x18000e992  call    cs:__imp_sprintf_s
0x18000e998  lea     rdx, a00002552552552; "0.0.0.0, 255.255.255.255"
0x18000e99f  lea     rcx, [rsp+108h+Buffer]; Str1
0x18000e9a7  call    strcmp_0
0x18000e9ac  test    eax, eax
0x18000e9ae  jnz     short loc_18000E9C2
0x18000e9b0  mov     edx, ebp; int
0x18000e9b2  mov     rcx, r14; this
0x18000e9b5  call    ?DeleteAllAddr@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllAddr(int)
0x18000e9ba  jmp     short loc_18000E9C2
0x18000e9bc  mov     [rsi+0E8h], ebp
0x18000e9c2  xor     eax, eax
0x18000e9c4  mov     rcx, [rsp+108h+var_38]
0x18000e9cc  xor     rcx, rsp; StackCookie
0x18000e9cf  call    __security_check_cookie
0x18000e9d4  add     rsp, 0E0h
0x18000e9db  pop     r14
0x18000e9dd  pop     rdi
0x18000e9de  pop     rsi
0x18000e9df  pop     rbp
0x18000e9e0  pop     rbx
0x18000e9e1  retn
```
