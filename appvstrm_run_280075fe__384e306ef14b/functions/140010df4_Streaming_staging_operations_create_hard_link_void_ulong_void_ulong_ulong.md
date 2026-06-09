# Streaming::staging_operations::create_hard_link(void *,ulong,void *,ulong,ulong &)

- ea: `0x140010df4`
- end: `0x140010ef7`
- name: `?create_hard_link@staging_operations@Streaming@@YAJPEAXK0KAEAK@Z`
- size: `259`
- prototype: `__int64 __fastcall(Streaming::staging_operations *__hidden this, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140013f68`

## callees

- `0x140007c24`
- `0x140010df4`

## pseudocode

```c
__int64 __fastcall Streaming::staging_operations::create_hard_link(
        Streaming::staging_operations *this,
        void *a2,
        _DWORD *a3,
        void *a4,
        _DWORD *a5)
{
  int v5; // r15d
  int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  __int64 v10; // r11
  __int64 v11; // rsi
  __int64 v12; // r14
  __int64 result; // rax
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING v15; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v16; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)(&v16.MaximumLength + 1) = 0;
  v5 = (int)a4;
  *(_DWORD *)(&v15.MaximumLength + 1) = 0;
  *(_DWORD *)(&v14.MaximumLength + 1) = 0;
  *a5 = 0;
  if ( !this )
    return 3221225485LL;
  if ( (unsigned int)a2 < 0x20 )
    return 3221225485LL;
  if ( (unsigned int)a2 < *((_DWORD *)this + 1) )
    return 3221225485LL;
  v7 = *((unsigned __int16 *)this + 6);
  if ( !(_WORD)v7 )
    return 3221225485LL;
  v8 = *((unsigned __int16 *)this + 10);
  if ( !(_WORD)v8 )
    return 3221225485LL;
  v9 = *((unsigned __int16 *)this + 14);
  if ( !(_WORD)v9 )
    return 3221225485LL;
  v10 = *((unsigned int *)this + 2);
  if ( (int)v10 + v7 > (unsigned int)a2 )
    return 3221225485LL;
  v11 = *((unsigned int *)this + 4);
  if ( (int)v11 + v8 > (unsigned int)a2 )
    return 3221225485LL;
  v12 = *((unsigned int *)this + 6);
  if ( (int)v12 + v9 > (unsigned int)a2 )
    return 3221225485LL;
  v16.Length = *((_WORD *)this + 6);
  v16.Buffer = (PWSTR)((char *)this + v10);
  v16.MaximumLength = v7;
  v15.Buffer = (PWSTR)((char *)this + v11);
  v15.Length = v8;
  v14.Buffer = (PWSTR)((char *)this + v12);
  v15.MaximumLength = v8;
  v14.Length = v9;
  v14.MaximumLength = v9;
  result = Streaming::Messaging::PackageLoader::CreateHardLink(&v16, &v15, &v14);
  if ( v5 != 4 || !a3 )
    return 3221225485LL;
  *a3 = result;
  *a5 = 4;
  return result;
}

```

## disassembly

```asm
0x140010df4  push    rbp
0x140010df6  push    rbx
0x140010df7  push    rsi
0x140010df8  push    rdi
0x140010df9  push    r12
0x140010dfb  push    r14
0x140010dfd  push    r15
0x140010dff  mov     rbp, rsp
0x140010e02  sub     rsp, 50h
0x140010e06  mov     rdi, qword ptr [rbp+arg_20]
0x140010e0a  xor     r12d, r12d
0x140010e0d  mov     dword ptr [rbp+var_10+4], r12d
0x140010e11  mov     r15d, r9d
0x140010e14  mov     dword ptr [rbp+var_20+4], r12d
0x140010e18  mov     rbx, r8
0x140010e1b  mov     dword ptr [rbp+var_30+4], r12d
0x140010e1f  mov     [rdi], r12d
0x140010e22  test    rcx, rcx
0x140010e25  jz      loc_140010EE2
0x140010e2b  cmp     edx, 20h ; ' '
0x140010e2e  jb      loc_140010EE2
0x140010e34  cmp     edx, [rcx+4]
0x140010e37  jb      loc_140010EE2
0x140010e3d  movzx   r8d, word ptr [rcx+0Ch]
0x140010e42  test    r8w, r8w
0x140010e46  jz      loc_140010EE2
0x140010e4c  movzx   r9d, word ptr [rcx+14h]
0x140010e51  test    r9w, r9w
0x140010e55  jz      loc_140010EE2
0x140010e5b  movzx   r10d, word ptr [rcx+1Ch]
0x140010e60  test    r10w, r10w
0x140010e64  jz      short loc_140010EE2
0x140010e66  mov     r11d, [rcx+8]
0x140010e6a  lea     eax, [r11+r8]
0x140010e6e  cmp     eax, edx
0x140010e70  ja      short loc_140010EE2
0x140010e72  mov     esi, [rcx+10h]
0x140010e75  lea     eax, [rsi+r9]
0x140010e79  cmp     eax, edx
0x140010e7b  ja      short loc_140010EE2
0x140010e7d  mov     r14d, [rcx+18h]
0x140010e81  lea     eax, [r14+r10]
0x140010e85  cmp     eax, edx
0x140010e87  ja      short loc_140010EE2
0x140010e89  lea     rax, [rcx+r11]
0x140010e8d  mov     [rbp+var_10.Length], r8w
0x140010e92  mov     [rbp+var_10.Buffer], rax
0x140010e96  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140010e9a  lea     rax, [rcx+rsi]
0x140010e9e  mov     [rbp+var_10.MaximumLength], r8w
0x140010ea3  mov     [rbp+var_20.Buffer], rax
0x140010ea7  lea     r8, [rbp+var_30]; struct _UNICODE_STRING *
0x140010eab  lea     rax, [rcx+r14]
0x140010eaf  mov     [rbp+var_20.Length], r9w
0x140010eb4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING *
0x140010eb8  mov     [rbp+var_30.Buffer], rax
0x140010ebc  mov     [rbp+var_20.MaximumLength], r9w
0x140010ec1  mov     [rbp+var_30.Length], r10w
0x140010ec6  mov     [rbp+var_30.MaximumLength], r10w
0x140010ecb  call    ?CreateHardLink@PackageLoader@Messaging@Streaming@@SAJAEBU_UNICODE_STRING@@00@Z; Streaming::Messaging::PackageLoader::CreateHardLink(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &)
0x140010ed0  cmp     r15d, 4
0x140010ed4  jnz     short loc_140010EE2
0x140010ed6  test    rbx, rbx
0x140010ed9  jz      short loc_140010EE2
0x140010edb  mov     [rbx], eax
0x140010edd  mov     [rdi], r15d
0x140010ee0  jmp     short loc_140010EE7
0x140010ee2  mov     eax, 0C000000Dh
0x140010ee7  add     rsp, 50h
0x140010eeb  pop     r15
0x140010eed  pop     r14
0x140010eef  pop     r12
0x140010ef1  pop     rdi
0x140010ef2  pop     rsi
0x140010ef3  pop     rbx
0x140010ef4  pop     rbp
0x140010ef5  retn
```
