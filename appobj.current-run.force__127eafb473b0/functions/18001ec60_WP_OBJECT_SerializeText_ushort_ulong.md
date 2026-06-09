# WP_OBJECT::SerializeText(ushort *,ulong)

- ea: `0x18001ec60`
- end: `0x18001ed0d`
- name: `?SerializeText@WP_OBJECT@@UEAAJPEAGK@Z`
- size: `173`
- prototype: `int(WP_OBJECT *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d654`
- `0x18001ec60`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ecf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ecf8`

## pseudocode

```c
__int64 __fastcall WP_OBJECT::SerializeText(WP_OBJECT *this, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v4; // rcx
  int v7; // ebx
  int v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  pv = 0;
  v4 = *((_QWORD *)this + 27);
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v4 + 56LL))(v4, &pv);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 27) + 24LL))(*((_QWORD *)this + 27), &v10);
    if ( v7 >= 0 )
    {
      v9 = v10;
      v7 = StringCchPrintfW(a2, a3, L"%ws \"%d\" (applicationPool:%ws)", L"WP", v9, pv);
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ec60  mov     [rsp+arg_8], rbx
0x18001ec65  push    rbp
0x18001ec66  push    rsi
0x18001ec67  push    rdi
0x18001ec68  sub     rsp, 30h
0x18001ec6c  mov     rdi, rcx
0x18001ec6f  mov     [rsp+48h+pv], 0
0x18001ec78  mov     rcx, [rcx+0D8h]
0x18001ec7f  mov     rbp, rdx
0x18001ec82  mov     [rsp+48h+arg_0], 0
0x18001ec8a  lea     rdx, [rsp+48h+pv]
0x18001ec8f  mov     esi, r8d
0x18001ec92  mov     rax, [rcx]
0x18001ec95  mov     rax, [rax+38h]
0x18001ec99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec9e  mov     ebx, eax
0x18001eca0  test    eax, eax
0x18001eca2  js      short loc_18001ECEE
0x18001eca4  mov     rcx, [rdi+0D8h]
0x18001ecab  lea     rdx, [rsp+48h+arg_0]
0x18001ecb0  mov     rax, [rcx]
0x18001ecb3  mov     rax, [rax+18h]
0x18001ecb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecbc  mov     ebx, eax
0x18001ecbe  test    eax, eax
0x18001ecc0  js      short loc_18001ECEE
0x18001ecc2  mov     rax, [rsp+48h+pv]
0x18001ecc7  lea     r9, aWp; "WP"
0x18001ecce  mov     [rsp+48h+var_20], rax
0x18001ecd3  lea     r8, aWsDApplication; "%ws \"%d\" (applicationPool:%ws)"
0x18001ecda  mov     eax, [rsp+48h+arg_0]
0x18001ecde  mov     edx, esi; unsigned __int64
0x18001ece0  mov     rcx, rbp; unsigned __int16 *
0x18001ece3  mov     [rsp+48h+var_28], eax
0x18001ece7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ecec  mov     ebx, eax
0x18001ecee  mov     rcx, [rsp+48h+pv]; pv
0x18001ecf3  test    rcx, rcx
0x18001ecf6  jz      short loc_18001ECFE
0x18001ecf8  call    cs:__imp_CoTaskMemFree
0x18001ecfe  mov     eax, ebx
0x18001ed00  mov     rbx, [rsp+48h+arg_8]
0x18001ed05  add     rsp, 30h
0x18001ed09  pop     rdi
0x18001ed0a  pop     rsi
0x18001ed0b  pop     rbp
0x18001ed0c  retn
```
