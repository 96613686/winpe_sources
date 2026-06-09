# CW32System::OleCreateStaticFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x18008fcfc`
- end: `0x18008fd8e`
- name: `?OleCreateStaticFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006c4c0`

## callees

- `0x180041adc`
- `0x18008fcfc`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008fd23`: `OleCreateStaticFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateStaticFromData(
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
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))((char *)Ole32Procs + 184);
  if ( !*((_QWORD *)Ole32Procs + 23) )
    SetProcAddr((FARPROC *)Ole32Procs + 23, 1, "OleCreateStaticFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18008fcfc  mov     [rsp+arg_0], rbx
0x18008fd01  mov     [rsp+arg_8], rsi
0x18008fd06  push    rdi
0x18008fd07  sub     rsp, 40h
0x18008fd0b  mov     rdi, r9
0x18008fd0e  mov     rsi, rcx
0x18008fd11  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008fd16  lea     rbx, [rax+0B8h]
0x18008fd1d  cmp     qword ptr [rbx], 0
0x18008fd21  jnz     short loc_18008FD37
0x18008fd23  lea     r8, aOlecreatestati; "OleCreateStaticFromData"
0x18008fd2a  mov     edx, 1
0x18008fd2f  mov     rcx, rbx
0x18008fd32  call    SetProcAddr
0x18008fd37  mov     rax, [rbx]
0x18008fd3a  test    rax, rax
0x18008fd3d  jz      short loc_18008FD79
0x18008fd3f  mov     rcx, [rsp+48h+arg_30]
0x18008fd47  lea     rdx, IID_IOleObject
0x18008fd4e  mov     [rsp+48h+var_18], rcx
0x18008fd53  mov     r9, rdi
0x18008fd56  mov     rcx, [rsp+48h+arg_28]
0x18008fd5b  mov     r8d, 1
0x18008fd61  mov     [rsp+48h+var_20], rcx
0x18008fd66  mov     rcx, rsi
0x18008fd69  mov     [rsp+48h+var_28], 0
0x18008fd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd77  jmp     short loc_18008FD7E
0x18008fd79  mov     eax, 80004005h
0x18008fd7e  mov     rbx, [rsp+48h+arg_0]
0x18008fd83  mov     rsi, [rsp+48h+arg_8]
0x18008fd88  add     rsp, 40h
0x18008fd8c  pop     rdi
0x18008fd8d  retn
```
