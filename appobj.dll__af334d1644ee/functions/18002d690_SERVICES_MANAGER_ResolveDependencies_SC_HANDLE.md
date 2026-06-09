# SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)

- ea: `0x18002d690`
- end: `0x18002d74a`
- name: `?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cfb8`
- `0x18002da9c`
- `0x18002dc60`

## callees

- `0x18002cd18`
- `0x18002d690`
- `0x18002d750`
- `0x1800342f4`

## string_xrefs

- `0x18002d70c`: `Unable to retrieve service name to list\n`
- `0x18002d718`: `SERVICES_MANAGER::ResolveDependencies`
- `0x18002d729`: `servercommon\inetsrv\iis\iisrearc\core\appcmd\dll\servicesmanager.cxx`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::ResolveDependencies(SERVICES_MANAGER *this, SC_HANDLE a2)
{
  bool v2; // zf
  signed int dwMessageId; // ebx
  unsigned int i; // edi
  char v8; // [rsp+30h] [rbp-18h]
  unsigned __int16 *v9; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 2) == 0;
  v9 = 0;
  if ( v2 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    dwMessageId = 0;
    for ( i = 0; i < *(_DWORD *)this; ++i )
    {
      dwMessageId = LIST_ARRAY::GetItem((SERVICES_MANAGER *)((char *)this + 8), i, (void **)&v9);
      if ( dwMessageId < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\appcmd\\dll\\servicesmanager.cxx",
            0x92u,
            "SERVICES_MANAGER::ResolveDependencies",
            dwMessageId,
            "Unable to retrieve service name to list\n",
            v8);
        return (unsigned int)dwMessageId;
      }
      dwMessageId = SERVICES_MANAGER::ResolveDependenciesRecursive(this, a2, v9, 1);
      if ( dwMessageId < 0 )
        return (unsigned int)dwMessageId;
    }
  }
  return (unsigned int)dwMessageId;
}

```

## disassembly

```asm
0x18002d690  mov     [rsp+arg_8], rbx
0x18002d695  mov     [rsp+arg_10], rbp
0x18002d69a  push    rsi
0x18002d69b  push    rdi
0x18002d69c  push    r14; char
0x18002d69e  sub     rsp, 30h
0x18002d6a2  cmp     dword ptr [rcx+8], 0
0x18002d6a6  mov     r14, rdx
0x18002d6a9  mov     rsi, rcx
0x18002d6ac  mov     [rsp+48h+arg_0], 0
0x18002d6b5  jnz     short loc_18002D6BE
0x18002d6b7  mov     ebx, 80004005h
0x18002d6bc  jmp     short loc_18002D735
0x18002d6be  xor     ebx, ebx
0x18002d6c0  xor     edi, edi
0x18002d6c2  cmp     edi, [rsi]
0x18002d6c4  jnb     short loc_18002D735
0x18002d6c6  lea     r8, [rsp+48h+arg_0]; void **
0x18002d6cb  mov     edx, edi; unsigned int
0x18002d6cd  lea     rcx, [rsi+8]; this
0x18002d6d1  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002d6d6  mov     ebx, eax
0x18002d6d8  test    eax, eax
0x18002d6da  js      short loc_18002D6FC
0x18002d6dc  mov     r8, [rsp+48h+arg_0]; unsigned __int16 *
0x18002d6e1  mov     r9d, 1; int
0x18002d6e7  mov     rdx, r14; struct SC_HANDLE__ *
0x18002d6ea  mov     rcx, rsi; this
0x18002d6ed  call    ?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z; SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)
0x18002d6f2  mov     ebx, eax
0x18002d6f4  test    eax, eax
0x18002d6f6  js      short loc_18002D735
0x18002d6f8  inc     edi
0x18002d6fa  jmp     short loc_18002D6C2
0x18002d6fc  test    cs:g_dwDebugFlags, 0Fh
0x18002d703  jz      short loc_18002D735
0x18002d705  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002d70c  lea     rax, aUnableToRetrie; "Unable to retrieve service name to list"...
0x18002d713  mov     [rsp+48h+var_20], rax; char *
0x18002d718  lea     r9, aServicesManage; "SERVICES_MANAGER::ResolveDependencies"
0x18002d71f  mov     r8d, 92h; unsigned int
0x18002d725  mov     [rsp+48h+dwMessageId], ebx; dwMessageId
0x18002d729  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002d730  call    PuDbgPrintError
0x18002d735  mov     rbp, [rsp+48h+arg_10]
0x18002d73a  mov     eax, ebx
0x18002d73c  mov     rbx, [rsp+48h+arg_8]
0x18002d741  add     rsp, 30h
0x18002d745  pop     r14
0x18002d747  pop     rdi
0x18002d748  pop     rsi
0x18002d749  retn
```
