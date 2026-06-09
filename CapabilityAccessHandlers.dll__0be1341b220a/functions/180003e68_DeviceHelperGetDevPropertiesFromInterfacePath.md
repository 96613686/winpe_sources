# DeviceHelperGetDevPropertiesFromInterfacePath

- ea: `0x180003e68`
- end: `0x180003fb4`
- name: `DeviceHelperGetDevPropertiesFromInterfacePath`
- size: `332`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003dc0`
- `0x180011760`

## callees

- `0x180003e68`
- `0x180003fbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f9b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003ec9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003f40`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003ec9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180003f40`

## pseudocode

```c
__int64 __fastcall DeviceHelperGetDevPropertiesFromInterfacePath(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v7; // rbx
  unsigned __int16 *v8; // rdi
  int ObjectProperties; // eax
  int v10; // esi
  int v11; // eax
  __int64 v12; // rbp
  unsigned __int16 v13; // cx
  int StringCopy; // eax
  LPVOID pv; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-50h] BYREF

  pv = 0;
  v17 = 0;
  v7 = 0;
  v8 = 0;
  if ( a6 )
    *a6 = 0;
  ObjectProperties = DevGetObjectProperties(1, a1, 0);
  v10 = ObjectProperties;
  if ( ObjectProperties >= 0 )
  {
    StringCopy = _DeviceHelperMakeStringCopy(a1, &v17);
    v8 = v17;
    v10 = StringCopy;
    goto LABEL_15;
  }
  if ( ObjectProperties != -2147024894 )
    return (unsigned int)v10;
  v11 = _DeviceHelperMakeStringCopy(a1, (unsigned __int16 **)&pv);
  v7 = (unsigned __int16 *)pv;
  if ( v11 >= 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)pv + v12) );
    while ( (unsigned int)v12 > 4 )
    {
      v13 = v7[(unsigned int)v12];
      v7[(unsigned int)v12] = 0;
      if ( v13 == 92 )
      {
        v10 = DevGetObjectProperties(1, v7, 0);
        if ( v10 >= 0 )
        {
          v8 = v7;
          v7 = 0;
          goto LABEL_16;
        }
      }
      LODWORD(v12) = v12 - 1;
    }
LABEL_15:
    if ( v10 >= 0 )
    {
LABEL_16:
      if ( a6 )
      {
        *a6 = v8;
        v8 = 0;
      }
    }
    goto LABEL_18;
  }
  v10 = v11;
LABEL_18:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003e68  push    rbx
0x180003e6a  push    rbp
0x180003e6b  push    rsi
0x180003e6c  push    rdi
0x180003e6d  push    r12
0x180003e6f  push    r13
0x180003e71  push    r14
0x180003e73  push    r15
0x180003e75  sub     rsp, 58h
0x180003e79  mov     r14, [rsp+98h+arg_28]
0x180003e81  xor     eax, eax
0x180003e83  mov     [rsp+98h+pv], rax
0x180003e88  mov     r15, r9
0x180003e8b  mov     [rsp+98h+var_50], rax
0x180003e90  mov     r12, r8
0x180003e93  mov     rbp, rcx
0x180003e96  mov     ebx, eax
0x180003e98  mov     edi, eax
0x180003e9a  test    r14, r14
0x180003e9d  jz      short loc_180003EA2
0x180003e9f  mov     [r14], rax
0x180003ea2  mov     r13, [rsp+98h+arg_20]
0x180003eaa  mov     eax, 1
0x180003eaf  mov     [rsp+98h+var_68], r13
0x180003eb4  mov     r9d, eax
0x180003eb7  mov     [rsp+98h+var_70], r15
0x180003ebc  xor     r8d, r8d
0x180003ebf  mov     rdx, rbp
0x180003ec2  mov     [rsp+98h+var_78], r12
0x180003ec7  mov     ecx, eax
0x180003ec9  call    cs:__imp_DevGetObjectProperties
0x180003ecf  mov     esi, eax
0x180003ed1  test    eax, eax
0x180003ed3  jns     loc_180003F5F
0x180003ed9  cmp     eax, 80070002h
0x180003ede  jnz     loc_180003FA1
0x180003ee4  lea     rdx, [rsp+98h+pv]; unsigned __int16 **
0x180003ee9  mov     rcx, rbp; unsigned __int16 *
0x180003eec  call    ?_DeviceHelperMakeStringCopy@@YAJPEBGPEAPEAG@Z; _DeviceHelperMakeStringCopy(ushort const *,ushort * *)
0x180003ef1  mov     rbx, [rsp+98h+pv]
0x180003ef6  xor     r8d, r8d
0x180003ef9  test    eax, eax
0x180003efb  js      short loc_180003F5B
0x180003efd  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180003f01  inc     rbp
0x180003f04  cmp     [rbx+rbp*2], r8w
0x180003f09  jnz     short loc_180003F01
0x180003f0b  cmp     ebp, 4
0x180003f0e  jbe     short loc_180003F76
0x180003f10  mov     edx, ebp
0x180003f12  movzx   ecx, word ptr [rbx+rdx*2]
0x180003f16  mov     [rbx+rdx*2], r8w
0x180003f1b  cmp     cx, 5Ch ; '\'
0x180003f1f  jnz     short loc_180003F4F
0x180003f21  mov     eax, 1
0x180003f26  mov     [rsp+98h+var_68], r13
0x180003f2b  mov     r9d, eax
0x180003f2e  mov     [rsp+98h+var_70], r15
0x180003f33  mov     ecx, eax
0x180003f35  mov     [rsp+98h+var_78], r12
0x180003f3a  xor     r8d, r8d
0x180003f3d  mov     rdx, rbx
0x180003f40  call    cs:__imp_DevGetObjectProperties
0x180003f46  xor     r8d, r8d
0x180003f49  mov     esi, eax
0x180003f4b  test    eax, eax
0x180003f4d  jns     short loc_180003F53
0x180003f4f  dec     ebp
0x180003f51  jmp     short loc_180003F0B
0x180003f53  mov     rdi, rbx
0x180003f56  mov     rbx, r8
0x180003f59  jmp     short loc_180003F7A
0x180003f5b  mov     esi, eax
0x180003f5d  jmp     short loc_180003F85
0x180003f5f  lea     rdx, [rsp+98h+var_50]; unsigned __int16 **
0x180003f64  mov     rcx, rbp; unsigned __int16 *
0x180003f67  call    ?_DeviceHelperMakeStringCopy@@YAJPEBGPEAPEAG@Z; _DeviceHelperMakeStringCopy(ushort const *,ushort * *)
0x180003f6c  mov     rdi, [rsp+98h+var_50]
0x180003f71  mov     esi, eax
0x180003f73  xor     r8d, r8d
0x180003f76  test    esi, esi
0x180003f78  js      short loc_180003F85
0x180003f7a  test    r14, r14
0x180003f7d  jz      short loc_180003F85
0x180003f7f  mov     [r14], rdi
0x180003f82  mov     rdi, r8
0x180003f85  test    rdi, rdi
0x180003f88  jz      short loc_180003F93
0x180003f8a  mov     rcx, rdi; pv
0x180003f8d  call    cs:__imp_CoTaskMemFree
0x180003f93  test    rbx, rbx
0x180003f96  jz      short loc_180003FA1
0x180003f98  mov     rcx, rbx; pv
0x180003f9b  call    cs:__imp_CoTaskMemFree
0x180003fa1  mov     eax, esi
0x180003fa3  add     rsp, 58h
0x180003fa7  pop     r15
0x180003fa9  pop     r14
0x180003fab  pop     r13
0x180003fad  pop     r12
0x180003faf  pop     rdi
0x180003fb0  pop     rsi
0x180003fb1  pop     rbp
0x180003fb2  pop     rbx
0x180003fb3  retn
```
