# CComAuthInfo2::UsesImpersonation(void)

- ea: `0x18001c558`
- end: `0x18001c579`
- name: `?UsesImpersonation@CComAuthInfo2@@QEBAHXZ`
- size: `33`
- prototype: `__int64 __fastcall(CComAuthInfo2 *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c0d4`

## callees

- `0x18001c558`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001c565`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c565`

## pseudocode

```c
_BOOL8 __fastcall CComAuthInfo2::UsesImpersonation(CComAuthInfo2 *this)
{
  OLECHAR *v1; // rcx

  v1 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v1 )
    LODWORD(v1) = SysStringLen(v1);
  return (_DWORD)v1 != 0;
}

```

## disassembly

```asm
0x18001c558  sub     rsp, 28h
0x18001c55c  mov     rcx, [rcx+8]; pbstr
0x18001c560  test    rcx, rcx
0x18001c563  jz      short loc_18001C56D
0x18001c565  call    cs:__imp_SysStringLen
0x18001c56b  mov     ecx, eax
0x18001c56d  xor     eax, eax
0x18001c56f  test    ecx, ecx
0x18001c571  setnz   al
0x18001c574  add     rsp, 28h
0x18001c578  retn
```
