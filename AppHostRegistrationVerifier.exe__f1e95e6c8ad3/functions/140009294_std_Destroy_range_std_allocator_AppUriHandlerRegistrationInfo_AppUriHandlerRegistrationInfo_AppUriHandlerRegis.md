# std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)

- ea: `0x140009294`
- end: `0x1400092c5`
- name: `??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z`
- size: `49`
- prototype: `void __fastcall(AppUriHandlerRegistrationInfo *this, AppUriHandlerRegistrationInfo *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092ec`
- `0x14000964c`
- `0x14000a204`
- `0x14000a474`
- `0x14000ed9c`

## callees

- `0x140009294`
- `0x14000a254`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(
        AppUriHandlerRegistrationInfo *this,
        AppUriHandlerRegistrationInfo *a2)
{
  AppUriHandlerRegistrationInfo *v3; // rbx

  if ( this != a2 )
  {
    v3 = this;
    do
    {
      AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo(v3);
      v3 = (AppUriHandlerRegistrationInfo *)((char *)v3 + 16);
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x140009294  cmp     rcx, rdx
0x140009297  jz      short locret_1400092C4
0x140009299  mov     [rsp+arg_0], rbx
0x14000929e  push    rdi
0x14000929f  sub     rsp, 20h
0x1400092a3  mov     rdi, rdx
0x1400092a6  mov     rbx, rcx
0x1400092a9  mov     rcx, rbx; this
0x1400092ac  call    ??1AppUriHandlerRegistrationInfo@@QEAA@XZ; AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo(void)
0x1400092b1  add     rbx, 10h
0x1400092b5  cmp     rbx, rdi
0x1400092b8  jnz     short loc_1400092A9
0x1400092ba  mov     rbx, [rsp+28h+arg_0]
0x1400092bf  add     rsp, 20h
0x1400092c3  pop     rdi
0x1400092c4  retn
```
