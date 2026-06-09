# _dynamic_atexit_destructor_for__g_comServer__

- ea: `0x180013ae0`
- end: `0x180013b2a`
- name: `_dynamic_atexit_destructor_for__g_comServer__`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012a64`
- `0x180013ae0`
- `0x180014010`

## pseudocode

```c
void __fastcall dynamic_atexit_destructor_for__g_comServer__(__int64 a1, struct ATL::_ATL_OBJMAP_ENTRY30 *a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rax

  v2 = off_18001E320;
  v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001E328;
  while ( v2 < v3 )
  {
    a2 = *v2;
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))a2 + 8))(0);
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001E328;
    }
    ++v2;
  }
  ATL::CAtlModule::~CAtlModule((ATL::CAtlModule *)&g_comServer, (unsigned int)a2);
}

```

## disassembly

```asm
0x180013ae0  push    rbx
0x180013ae2  sub     rsp, 20h
0x180013ae6  mov     rbx, cs:off_18001E320
0x180013aed  mov     rax, cs:off_18001E328
0x180013af4  jmp     short loc_180013B14
0x180013af6  mov     rdx, [rbx]
0x180013af9  test    rdx, rdx
0x180013afc  jz      short loc_180013B10
0x180013afe  mov     rax, [rdx+40h]
0x180013b02  xor     ecx, ecx
0x180013b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b09  mov     rax, cs:off_18001E328
0x180013b10  add     rbx, 8
0x180013b14  cmp     rbx, rax
0x180013b17  jb      short loc_180013AF6
0x180013b19  lea     rcx, ?g_comServer@@3VDmrcComServer@@A; this
0x180013b20  add     rsp, 20h
0x180013b24  pop     rbx
0x180013b25  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
