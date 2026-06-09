# MemoryStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180017750`
- end: `0x18001780f`
- name: `?Stat@MemoryStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `191`
- prototype: `__int64 __fastcall(MemoryStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000c7fc`
- `0x180017750`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001779b`
- `ole32!CoTaskMemAlloc` at `0x18001779b`

## pseudocode

```c
__int64 __fastcall MemoryStream::Stat(MemoryStream *this, struct tagSTATSTG *a2, char a3)
{
  __int64 result; // rax
  OLECHAR *v6; // rax
  wchar_t v7[20]; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( (a3 & 1) != 0 )
  {
    a2->pwcsName = 0;
  }
  else
  {
    wcscpy(v7, L"MeyStream");
    v6 = (OLECHAR *)CoTaskMemAlloc(0x1Au);
    a2->pwcsName = v6;
    if ( v6 )
      StringCchCopyW(v6, 0xDu, v7);
  }
  a2->type = 2;
  a2->cbSize.QuadPart = *((_QWORD *)this + 3) - *((_QWORD *)this + 2);
  result = 0;
  a2->mtime = 0;
  a2->ctime = 0;
  a2->atime = 0;
  *(_QWORD *)&a2->grfMode = 0;
  a2->clsid = GUID_NULL;
  *(_QWORD *)&a2->grfStateBits = 0;
  return result;
}

```

## disassembly

```asm
0x180017750  mov     [rsp+arg_0], rbx
0x180017755  push    rdi
0x180017756  sub     rsp, 40h
0x18001775a  mov     rbx, rdx
0x18001775d  mov     rdi, rcx
0x180017760  test    rdx, rdx
0x180017763  jnz     short loc_18001776F
0x180017765  mov     eax, 80070057h
0x18001776a  jmp     loc_180017804
0x18001776f  test    r8b, 1
0x180017773  jz      short loc_18001777E
0x180017775  mov     qword ptr [rdx], 0
0x18001777c  jmp     short loc_1800177BB
0x18001777e  movups  xmm0, xmmword ptr cs:aMemorystream; "MemoryStream"
0x180017785  mov     ecx, 1Ah; cb
0x18001778a  movups  xmm1, xmmword ptr cs:aMemorystream+0Ah; "yStream"
0x180017791  movups  xmmword ptr [rsp+48h+var_28], xmm0
0x180017796  movups  xmmword ptr [rsp+48h+var_28+0Ah], xmm1
0x18001779b  call    cs:__imp_CoTaskMemAlloc
0x1800177a1  mov     [rbx], rax
0x1800177a4  test    rax, rax
0x1800177a7  jz      short loc_1800177BB
0x1800177a9  lea     r8, [rsp+48h+var_28]; wchar_t *
0x1800177ae  mov     edx, 0Dh; unsigned __int64
0x1800177b3  mov     rcx, rax; wchar_t *
0x1800177b6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800177bb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800177c2  mov     dword ptr [rbx+8], 2
0x1800177c9  mov     rax, [rdi+18h]
0x1800177cd  sub     rax, [rdi+10h]
0x1800177d1  mov     [rbx+10h], rax
0x1800177d5  xor     eax, eax
0x1800177d7  mov     qword ptr [rbx+18h], 0
0x1800177df  mov     qword ptr [rbx+20h], 0
0x1800177e7  mov     qword ptr [rbx+28h], 0
0x1800177ef  mov     qword ptr [rbx+30h], 0
0x1800177f7  movdqu  xmmword ptr [rbx+38h], xmm0
0x1800177fc  mov     qword ptr [rbx+48h], 0
0x180017804  mov     rbx, [rsp+48h+arg_0]
0x180017809  add     rsp, 40h
0x18001780d  pop     rdi
0x18001780e  retn
```
