# PiRegStateOpenClassKey

- ea: `0x140037b70`
- end: `0x140037cfb`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140037eec`
- `0x140038058`

## callees

- `0x1400079f0`
- `0x140037b70`
- `0x140038340`
- `0x140038410`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140037cb1`
- `ntoskrnl!ZwClose` at `0x140037cb1`
- `ntoskrnl!_snwprintf` at `0x140037c51`
- `ntoskrnl!_snwprintf` at `0x140037c51`

## string_xrefs

- `0x140037bca`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
int __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, ULONG *a4, _QWORD *a5)
{
  int result; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  HANDLE v11; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // esi
  int v14; // edi
  ULONG v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h]
  __int64 v17; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17 = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class");
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      v12 = CmRegUtilCreateWstrKey((__int64)Handle, Dest, v9, v10, 0, &v15, &v17);
      v13 = v15;
    }
    else
    {
      v12 = CmRegUtilOpenExistingWstrKey(Handle, Dest);
      v13 = 2;
    }
    v14 = v12;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17;
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140037b70  mov     [rsp-8+arg_8], rbx
0x140037b75  push    rbp
0x140037b76  push    rsi
0x140037b77  push    rdi
0x140037b78  push    r12
0x140037b7a  push    r13
0x140037b7c  push    r14
0x140037b7e  push    r15
0x140037b80  lea     rbp, [rsp-1Fh]
0x140037b85  sub     rsp, 0F0h
0x140037b8c  mov     rax, cs:__security_cookie
0x140037b93  xor     rax, rsp
0x140037b96  mov     [rbp+4Fh+var_40], rax
0x140037b9a  mov     r12, [rbp+4Fh+arg_20]
0x140037b9e  xor     ebx, ebx
0x140037ba0  mov     [rbp+4Fh+Handle], rbx
0x140037ba4  mov     r14, r9
0x140037ba7  mov     [rbp+4Fh+var_A0], rbx
0x140037bab  mov     r13d, r8d
0x140037bae  mov     [rbp+4Fh+var_B0], ebx
0x140037bb1  mov     r15, rcx
0x140037bb4  mov     [r12], rbx
0x140037bb8  test    r9, r9
0x140037bbb  jz      short loc_140037BC0
0x140037bbd  mov     [r9], ebx
0x140037bc0  lea     r9, [rbp+4Fh+Handle]
0x140037bc4  mov     r8d, 20019h
0x140037bca  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x140037bd1  xor     ecx, ecx
0x140037bd3  call    CmRegUtilOpenExistingWstrKey
0x140037bd8  test    eax, eax
0x140037bda  js      loc_140037CD3
0x140037be0  movzx   ecx, byte ptr [r15+0Eh]
0x140037be5  movzx   edx, byte ptr [r15+0Dh]
0x140037bea  movzx   r8d, byte ptr [r15+0Ch]
0x140037bef  movzx   r9d, byte ptr [r15+0Bh]
0x140037bf4  movzx   eax, byte ptr [r15+0Fh]
0x140037bf9  movzx   r10d, byte ptr [r15+0Ah]
0x140037bfe  movzx   r11d, byte ptr [r15+9]
0x140037c03  movzx   ebx, byte ptr [r15+8]
0x140037c08  movzx   edi, word ptr [r15+6]
0x140037c0d  movzx   esi, word ptr [r15+4]
0x140037c12  mov     [rsp+120h+var_B8], eax
0x140037c16  mov     [rsp+120h+var_C0], ecx
0x140037c1a  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140037c1e  mov     [rsp+120h+var_C8], edx
0x140037c22  mov     edx, 27h ; '''; Count
0x140037c27  mov     [rsp+120h+var_D0], r8d
0x140037c2c  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140037c33  mov     [rsp+120h+var_D8], r9d
0x140037c38  mov     r9d, [r15]
0x140037c3b  mov     [rsp+120h+var_E0], r10d
0x140037c40  mov     [rsp+120h+var_E8], r11d
0x140037c45  mov     dword ptr [rsp+120h+var_F0], ebx
0x140037c49  mov     dword ptr [rsp+120h+var_F8], edi
0x140037c4d  mov     dword ptr [rsp+120h+var_100], esi
0x140037c51  call    cs:__imp__snwprintf
0x140037c58  nop     dword ptr [rax+rax+00h]
0x140037c5d  mov     rbx, [rbp+4Fh+Handle]
0x140037c61  lea     rdx, [rbp+4Fh+Dest]
0x140037c65  xor     eax, eax
0x140037c67  mov     rcx, rbx
0x140037c6a  mov     [rbp+4Fh+var_44], ax
0x140037c6e  test    r13d, r13d
0x140037c71  jz      short loc_140037C98
0x140037c73  lea     rax, [rbp+4Fh+var_A0]
0x140037c77  mov     [rsp+120h+var_F0], rax
0x140037c7c  lea     rax, [rbp+4Fh+var_B0]
0x140037c80  mov     [rsp+120h+var_F8], rax
0x140037c85  mov     [rsp+120h+var_100], 0
0x140037c8e  call    CmRegUtilCreateWstrKey
0x140037c93  mov     esi, [rbp+4Fh+var_B0]
0x140037c96  jmp     short loc_140037CAC
0x140037c98  lea     r9, [rbp+4Fh+var_A0]
0x140037c9c  mov     r8d, 0F003Fh
0x140037ca2  call    CmRegUtilOpenExistingWstrKey
0x140037ca7  mov     esi, 2
0x140037cac  mov     rcx, rbx; Handle
0x140037caf  mov     edi, eax
0x140037cb1  call    cs:__imp_ZwClose
0x140037cb8  nop     dword ptr [rax+rax+00h]
0x140037cbd  test    edi, edi
0x140037cbf  js      short loc_140037CD1
0x140037cc1  mov     rax, [rbp+4Fh+var_A0]
0x140037cc5  mov     [r12], rax
0x140037cc9  test    r14, r14
0x140037ccc  jz      short loc_140037CD1
0x140037cce  mov     [r14], esi
0x140037cd1  mov     eax, edi
0x140037cd3  mov     rcx, [rbp+4Fh+var_40]
0x140037cd7  xor     rcx, rsp; StackCookie
0x140037cda  call    __security_check_cookie
0x140037cdf  mov     rbx, [rsp+120h+arg_8]
0x140037ce7  add     rsp, 0F0h
0x140037cee  pop     r15
0x140037cf0  pop     r14
0x140037cf2  pop     r13
0x140037cf4  pop     r12
0x140037cf6  pop     rdi
0x140037cf7  pop     rsi
0x140037cf8  pop     rbp
0x140037cf9  retn
```
