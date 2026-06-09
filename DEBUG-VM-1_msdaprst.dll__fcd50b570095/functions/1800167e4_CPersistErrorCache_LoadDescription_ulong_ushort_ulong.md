# CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)

- ea: `0x1800167e4`
- end: `0x180016874`
- name: `?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z`
- size: `144`
- prototype: `void(CPersistErrorCache *__hidden this, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001616c`

## callees

- `0x18000c8b4`
- `0x1800167e4`
- `0x18001687c`
- `0x18002e02a`

## import_xrefs

- `USER32!LoadStringW` at `0x18001683b`
- `USER32!LoadStringW` at `0x18001683b`

## string_xrefs

- `0x180016849`: `Can not load msdaprsr.dll.`

## pseudocode

```c
void __fastcall CPersistErrorCache::LoadDescription(CPersistErrorCache *this, UINT a2, unsigned __int16 *a3)
{
  HINSTANCE v3; // rbx

  v3 = g_hinstance_PersistR;
  if ( (g_hinstance_PersistR || (LoadPersistR(), (v3 = g_hinstance_PersistR) != 0)) && a2 != 137 )
  {
    memset_0(a3, 0, 0x400u);
    LoadStringW(v3, a2, a3, 1024);
  }
  else
  {
    StringCchCopyNW(a3, 0x400u, L"Can not load msdaprsr.dll.", 0x400u);
    a3[1023] = 0;
  }
}

```

## disassembly

```asm
0x1800167e4  mov     [rsp+arg_0], rbx
0x1800167e9  mov     [rsp+arg_8], rbp
0x1800167ee  push    rsi
0x1800167ef  sub     rsp, 20h
0x1800167f3  mov     rbx, cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_PersistR
0x1800167fa  mov     rsi, r8
0x1800167fd  mov     ebp, edx
0x1800167ff  test    rbx, rbx
0x180016802  jnz     short loc_180016815
0x180016804  call    ?LoadPersistR@@YAXXZ; LoadPersistR(void)
0x180016809  mov     rbx, cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_PersistR
0x180016810  test    rbx, rbx
0x180016813  jz      short loc_180016843
0x180016815  cmp     ebp, 89h
0x18001681b  jz      short loc_180016843
0x18001681d  xor     edx, edx; Val
0x18001681f  mov     r8d, 400h; Size
0x180016825  mov     rcx, rsi; void *
0x180016828  call    memset_0
0x18001682d  mov     r9d, 400h; cchBufferMax
0x180016833  mov     r8, rsi; lpBuffer
0x180016836  mov     edx, ebp; uID
0x180016838  mov     rcx, rbx; hInstance
0x18001683b  call    cs:__imp_LoadStringW
0x180016841  jmp     short loc_180016864
0x180016843  mov     r9d, 400h; unsigned __int64
0x180016849  lea     r8, aCanNotLoadMsda; "Can not load msdaprsr.dll."
0x180016850  mov     edx, r9d; unsigned __int64
0x180016853  mov     rcx, rsi; unsigned __int16 *
0x180016856  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001685b  xor     eax, eax
0x18001685d  mov     [rsi+7FEh], ax
0x180016864  mov     rbx, [rsp+28h+arg_0]
0x180016869  mov     rbp, [rsp+28h+arg_8]
0x18001686e  add     rsp, 20h
0x180016872  pop     rsi
0x180016873  retn
```
