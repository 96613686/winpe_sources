# ServiceManager::StartUnifiedStackOperation(void)

- ea: `0x18001d5c4`
- end: `0x18001d671`
- name: `?StartUnifiedStackOperation@ServiceManager@@AEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18001d224`

## callees

- `0x18000f67c`
- `0x18001d5c4`

## import_xrefs

- `MapsStore!MapsStore_InstallAsync` at `0x18001d640`
- `MapsStore!MapsStore_InstallAsync` at `0x18001d640`
- `MapsStore!MapsStore_UpdateAsync` at `0x18001d5e4`
- `MapsStore!MapsStore_UpdateAsync` at `0x18001d5e4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d65c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d65c`

## string_xrefs

- `0x18001d653`: `ServiceManager::StartUnifiedStackOperation`

## pseudocode

```c
__int64 __fastcall ServiceManager::StartUnifiedStackOperation(ServiceManager *this)
{
  bool v1; // zf
  int updated; // eax
  unsigned int v4; // ebx
  int v5; // r8d
  char CurrentOperationInfo; // al
  int v7; // r8d
  unsigned __int8 v8; // al
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 880) == 3;
  *((_DWORD *)this + 881) = 4;
  if ( v1 )
  {
    updated = MapsStore_UpdateAsync();
    v4 = 0;
    if ( updated < 0 )
    {
      v5 = 2032;
      return (unsigned int)ZTraceReportPropagation(updated, "ServiceManager::StartUnifiedStackOperation", v5, this);
    }
  }
  else
  {
    CurrentOperationInfo = PackageManager::GetCurrentOperationInfo((ServiceManager *)((char *)this + 3568));
    v7 = CurrentOperationInfo & 2;
    v10 = *((_DWORD *)this + 952);
    v8 = CurrentOperationInfo & 1;
    v4 = 0;
    if ( !v10 )
      __int2c();
    if ( !v7 && !v8 )
      __int2c();
    updated = MapsStore_InstallAsync(&v10, v7 != 0, &v10, v8);
    if ( updated < 0 )
    {
      v5 = 2048;
      return (unsigned int)ZTraceReportPropagation(updated, "ServiceManager::StartUnifiedStackOperation", v5, this);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001d5c4  mov     [rsp+arg_8], rbx
0x18001d5c9  push    rdi
0x18001d5ca  sub     rsp, 20h
0x18001d5ce  cmp     dword ptr [rcx+0DC0h], 3
0x18001d5d5  mov     rdi, rcx
0x18001d5d8  mov     dword ptr [rcx+0DC4h], 4
0x18001d5e2  jnz     short loc_18001D5F8
0x18001d5e4  call    cs:__imp_?MapsStore_UpdateAsync@@YAJXZ; MapsStore_UpdateAsync(void)
0x18001d5ea  xor     ebx, ebx
0x18001d5ec  test    eax, eax
0x18001d5ee  jns     short loc_18001D664
0x18001d5f0  mov     r8d, 7F0h
0x18001d5f6  jmp     short loc_18001D650
0x18001d5f8  add     rcx, 0DF0h; this
0x18001d5ff  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x18001d604  mov     ecx, [rdi+0EE0h]
0x18001d60a  mov     r8d, eax
0x18001d60d  and     r8d, 2
0x18001d611  mov     [rsp+28h+arg_0], ecx
0x18001d615  and     al, 1
0x18001d617  xor     ebx, ebx
0x18001d619  test    ecx, ecx
0x18001d61b  jnz     short loc_18001D61F
0x18001d61d  int     2Ch; Windows NT - assertion failure
0x18001d61f  test    r8d, r8d
0x18001d622  jnz     short loc_18001D62A
0x18001d624  test    al, al
0x18001d626  jnz     short loc_18001D62A
0x18001d628  int     2Ch; Windows NT - assertion failure
0x18001d62a  test    r8d, r8d
0x18001d62d  movzx   r9d, al
0x18001d631  mov     edx, ebx
0x18001d633  lea     r8, [rsp+28h+arg_0]
0x18001d638  setnz   dl
0x18001d63b  lea     rcx, [rsp+28h+arg_0]
0x18001d640  call    cs:__imp_?MapsStore_InstallAsync@@YAJPEAIK0K@Z; MapsStore_InstallAsync(uint *,ulong,uint *,ulong)
0x18001d646  test    eax, eax
0x18001d648  jns     short loc_18001D664
0x18001d64a  mov     r8d, 800h
0x18001d650  mov     r9, rdi
0x18001d653  lea     rdx, aServicemanager_82; "ServiceManager::StartUnifiedStackOperat"...
0x18001d65a  mov     ecx, eax
0x18001d65c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001d662  mov     ebx, eax
0x18001d664  mov     eax, ebx
0x18001d666  mov     rbx, [rsp+28h+arg_8]
0x18001d66b  add     rsp, 20h
0x18001d66f  pop     rdi
0x18001d670  retn
```
