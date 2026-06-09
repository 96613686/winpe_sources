# _dynamic_atexit_destructor_for__g_Globals__

- ea: `0x1800a7800`
- end: `0x1800a78b9`
- name: `_dynamic_atexit_destructor_for__g_Globals__`
- size: `185`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800345a0`
- `0x180036024`
- `0x180046c00`
- `0x1800a7800`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7896`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7896`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__g_Globals__()
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v0; // rbx
  __int64 *v1; // rax

  g_Globals = (__int64)&ShaderCacheGlobals::`vftable';
  sqlite3_shutdown();
  v0 = off_1800C66B0;
  v1 = off_1800C66B8;
  while ( v0 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v1 )
  {
    if ( *v0 )
    {
      (*((void (__fastcall **)(_QWORD))*v0 + 8))(0);
      v1 = off_1800C66B8;
    }
    ++v0;
  }
  if ( dword_1800C7468 )
  {
    if ( qword_1800C7470 )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&dword_1800C7468);
      qword_1800C7470 = 0;
    }
    if ( qword_1800C74A0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800C74A0 + 16LL))(qword_1800C74A0);
    DeleteCriticalSection(&stru_1800C7478);
    dword_1800C7468 = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&dword_1800C7468);
}

```

## disassembly

```asm
0x1800a7800  push    rbx
0x1800a7802  sub     rsp, 20h
0x1800a7806  lea     rax, ??_7ShaderCacheGlobals@@6B@; const ShaderCacheGlobals::`vftable'
0x1800a780d  mov     cs:?g_Globals@@3VShaderCacheGlobals@@A, rax; ShaderCacheGlobals g_Globals
0x1800a7814  call    sqlite3_shutdown
0x1800a7819  nop
0x1800a781a  mov     rbx, cs:off_1800C66B0
0x1800a7821  mov     rax, cs:off_1800C66B8
0x1800a7828  jmp     short loc_1800A7848
0x1800a782a  mov     rdx, [rbx]
0x1800a782d  test    rdx, rdx
0x1800a7830  jz      short loc_1800A7844
0x1800a7832  xor     ecx, ecx
0x1800a7834  mov     rax, [rdx+40h]
0x1800a7838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a783d  mov     rax, cs:off_1800C66B8
0x1800a7844  add     rbx, 8
0x1800a7848  cmp     rbx, rax
0x1800a784b  jb      short loc_1800A782A
0x1800a784d  cmp     cs:dword_1800C7468, 0
0x1800a7854  jz      short loc_1800A78A6
0x1800a7856  cmp     cs:qword_1800C7470, 0
0x1800a785e  jz      short loc_1800A7877
0x1800a7860  lea     rcx, dword_1800C7468; struct ATL::_ATL_MODULE70 *
0x1800a7867  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800a786c  mov     cs:qword_1800C7470, 0
0x1800a7877  mov     rcx, cs:qword_1800C74A0
0x1800a787e  test    rcx, rcx
0x1800a7881  jz      short loc_1800A788F
0x1800a7883  mov     rax, [rcx]
0x1800a7886  mov     rax, [rax+10h]
0x1800a788a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a788f  lea     rcx, stru_1800C7478; lpCriticalSection
0x1800a7896  call    cs:__imp_DeleteCriticalSection
0x1800a789c  mov     cs:dword_1800C7468, 0
0x1800a78a6  lea     rcx, dword_1800C7468
0x1800a78ad  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800a78b2  nop
0x1800a78b3  add     rsp, 20h
0x1800a78b7  pop     rbx
0x1800a78b8  retn
```
