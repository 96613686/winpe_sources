# CW32System::OleCreateLinkFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x18008fc64`
- end: `0x18008fcf6`
- name: `?OleCreateLinkFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006c4c0`

## callees

- `0x180041adc`
- `0x18008fc64`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008fc8b`: `OleCreateLinkFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateLinkFromData(
        struct IDataObject *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct tagFORMATETC *a4,
        struct IOleClientSite *a5,
        struct IStorage *a6,
        void **a7)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v10)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))((char *)Ole32Procs + 176);
  if ( !*((_QWORD *)Ole32Procs + 22) )
    SetProcAddr((FARPROC *)Ole32Procs + 22, 1, "OleCreateLinkFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18008fc64  mov     [rsp+arg_0], rbx
0x18008fc69  mov     [rsp+arg_8], rsi
0x18008fc6e  push    rdi
0x18008fc6f  sub     rsp, 40h
0x18008fc73  mov     rdi, r9
0x18008fc76  mov     rsi, rcx
0x18008fc79  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008fc7e  lea     rbx, [rax+0B0h]
0x18008fc85  cmp     qword ptr [rbx], 0
0x18008fc89  jnz     short loc_18008FC9F
0x18008fc8b  lea     r8, aOlecreatelinkf; "OleCreateLinkFromData"
0x18008fc92  mov     edx, 1
0x18008fc97  mov     rcx, rbx
0x18008fc9a  call    SetProcAddr
0x18008fc9f  mov     rax, [rbx]
0x18008fca2  test    rax, rax
0x18008fca5  jz      short loc_18008FCE1
0x18008fca7  mov     rcx, [rsp+48h+arg_30]
0x18008fcaf  lea     rdx, IID_IOleObject
0x18008fcb6  mov     [rsp+48h+var_18], rcx
0x18008fcbb  mov     r9, rdi
0x18008fcbe  mov     rcx, [rsp+48h+arg_28]
0x18008fcc3  mov     r8d, 1
0x18008fcc9  mov     [rsp+48h+var_20], rcx
0x18008fcce  mov     rcx, rsi
0x18008fcd1  mov     [rsp+48h+var_28], 0
0x18008fcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fcdf  jmp     short loc_18008FCE6
0x18008fce1  mov     eax, 80004005h
0x18008fce6  mov     rbx, [rsp+48h+arg_0]
0x18008fceb  mov     rsi, [rsp+48h+arg_8]
0x18008fcf0  add     rsp, 40h
0x18008fcf4  pop     rdi
0x18008fcf5  retn
```
