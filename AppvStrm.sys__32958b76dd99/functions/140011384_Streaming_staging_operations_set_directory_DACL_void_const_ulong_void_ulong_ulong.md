# Streaming::staging_operations::set_directory_DACL(void const *,ulong,void *,ulong,ulong &)

- ea: `0x140011384`
- end: `0x140011470`
- name: `?set_directory_DACL@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z`
- size: `236`
- prototype: `int __fastcall(Streaming::staging_operations *this, const void *, int *, void *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140013f68`

## callees

- `0x1400020c8`
- `0x140011384`

## pseudocode

```c
int __fastcall Streaming::staging_operations::set_directory_DACL(
        Streaming::staging_operations *this,
        const void *a2,
        int *a3,
        void *a4,
        _DWORD *a5)
{
  int v5; // ebp
  int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  __int64 v10; // r11
  __int64 v11; // rsi
  __int64 v12; // r14
  int result; // eax
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING v15; // [rsp+30h] [rbp-48h] BYREF

  *(_DWORD *)(&v15.MaximumLength + 1) = 0;
  v5 = (int)a4;
  *(_DWORD *)(&v14.MaximumLength + 1) = 0;
  *a5 = 0;
  if ( !this )
    return -1073741811;
  if ( (unsigned int)a2 < 0x20 )
    return -1073741811;
  if ( (unsigned int)a2 < *((_DWORD *)this + 1) )
    return -1073741811;
  v7 = *((unsigned __int16 *)this + 6);
  if ( !(_WORD)v7 )
    return -1073741811;
  v8 = *((unsigned __int16 *)this + 10);
  if ( !(_WORD)v8 )
    return -1073741811;
  v9 = *((_DWORD *)this + 7);
  if ( !v9 )
    return -1073741811;
  v10 = *((unsigned int *)this + 2);
  if ( (int)v10 + v7 > (unsigned int)a2 )
    return -1073741811;
  v11 = *((unsigned int *)this + 4);
  if ( (int)v11 + v8 > (unsigned int)a2 )
    return -1073741811;
  v12 = *((unsigned int *)this + 6);
  if ( (int)v12 + v9 > (unsigned int)a2 )
    return -1073741811;
  v15.Length = *((_WORD *)this + 6);
  v15.Buffer = (PWSTR)((char *)this + v10);
  v15.MaximumLength = v7;
  v14.Buffer = (PWSTR)((char *)this + v11);
  v14.Length = v8;
  v14.MaximumLength = v8;
  result = Streaming::DACLSetter::SetDirectoryDACL(&v15, &v14, (char *)this + v12);
  if ( v5 != 4 || !a3 )
    return -1073741811;
  *a3 = result;
  *a5 = 4;
  return result;
}

```

## disassembly

```asm
0x140011384  push    rbx
0x140011386  push    rbp
0x140011387  push    rsi
0x140011388  push    rdi
0x140011389  push    r14
0x14001138b  push    r15
0x14001138d  sub     rsp, 48h
0x140011391  mov     rdi, qword ptr [rsp+78h+arg_20]
0x140011399  xor     r15d, r15d
0x14001139c  mov     dword ptr [rsp+78h+var_48+4], r15d
0x1400113a1  mov     ebp, r9d
0x1400113a4  mov     dword ptr [rsp+78h+var_58+4], r15d
0x1400113a9  mov     rbx, r8
0x1400113ac  mov     [rdi], r15d
0x1400113af  test    rcx, rcx
0x1400113b2  jz      loc_14001145D
0x1400113b8  cmp     edx, 20h ; ' '
0x1400113bb  jb      loc_14001145D
0x1400113c1  cmp     edx, [rcx+4]
0x1400113c4  jb      loc_14001145D
0x1400113ca  movzx   r8d, word ptr [rcx+0Ch]
0x1400113cf  test    r8w, r8w
0x1400113d3  jz      loc_14001145D
0x1400113d9  movzx   r9d, word ptr [rcx+14h]
0x1400113de  test    r9w, r9w
0x1400113e2  jz      short loc_14001145D
0x1400113e4  mov     r10d, [rcx+1Ch]
0x1400113e8  test    r10d, r10d
0x1400113eb  jz      short loc_14001145D
0x1400113ed  mov     r11d, [rcx+8]
0x1400113f1  lea     eax, [r11+r8]
0x1400113f5  cmp     eax, edx
0x1400113f7  ja      short loc_14001145D
0x1400113f9  mov     esi, [rcx+10h]
0x1400113fc  lea     eax, [rsi+r9]
0x140011400  cmp     eax, edx
0x140011402  ja      short loc_14001145D
0x140011404  mov     r14d, [rcx+18h]
0x140011408  lea     eax, [r14+r10]
0x14001140c  cmp     eax, edx
0x14001140e  ja      short loc_14001145D
0x140011410  lea     rax, [rcx+r11]
0x140011414  mov     [rsp+78h+var_48.Length], r8w
0x14001141a  mov     [rsp+78h+var_48.Buffer], rax
0x14001141f  lea     rdx, [rsp+78h+var_58]; struct _UNICODE_STRING *
0x140011424  lea     rax, [rcx+rsi]
0x140011428  mov     [rsp+78h+var_48.MaximumLength], r8w
0x14001142e  lea     r8, [rcx+r14]; void *
0x140011432  mov     [rsp+78h+var_58.Buffer], rax
0x140011437  lea     rcx, [rsp+78h+var_48]; struct _UNICODE_STRING *
0x14001143c  mov     [rsp+78h+var_58.Length], r9w
0x140011442  mov     [rsp+78h+var_58.MaximumLength], r9w
0x140011448  call    ?SetDirectoryDACL@DACLSetter@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAX@Z; Streaming::DACLSetter::SetDirectoryDACL(_UNICODE_STRING const &,_UNICODE_STRING const &,void *)
0x14001144d  cmp     ebp, 4
0x140011450  jnz     short loc_14001145D
0x140011452  test    rbx, rbx
0x140011455  jz      short loc_14001145D
0x140011457  mov     [rbx], eax
0x140011459  mov     [rdi], ebp
0x14001145b  jmp     short loc_140011462
0x14001145d  mov     eax, 0C000000Dh
0x140011462  add     rsp, 48h
0x140011466  pop     r15
0x140011468  pop     r14
0x14001146a  pop     rdi
0x14001146b  pop     rsi
0x14001146c  pop     rbp
0x14001146d  pop     rbx
0x14001146e  retn
```
