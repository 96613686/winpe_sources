# TiCoreInitializeNonCBSHostedService

- ea: `0x14000ce08`
- end: `0x14000ceac`
- name: `TiCoreInitializeNonCBSHostedService`
- size: `164`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140009438`

## callees

- `0x140002070`
- `0x14000ce08`
- `0x140013d88`
- `0x140017658`

## string_xrefs

- `0x14000ce83`: `Failed to allocate class factory for service:%d`

## pseudocode

```c
__int64 __fastcall TiCoreInitializeNonCBSHostedService(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  CCbsPublicFacadeClassFactory *v5; // rax
  CCbsPublicFacadeClassFactory *v6; // rax
  char *v7; // rax

  if ( a2 )
  {
    v5 = (CCbsPublicFacadeClassFactory *)operator new(0x38u);
    if ( v5
      && (v6 = CCbsPublicFacadeClassFactory::CCbsPublicFacadeClassFactory(v5, a1)) != 0
      && (v7 = (char *)v6 + *(int *)(*((_QWORD *)v6 + 1) + 4LL) + 8) != 0 )
    {
      v4 = 0;
      *a2 = v7;
    }
    else
    {
      v4 = -2147024882;
      CBSWdsLogLight(0x4000000, 2147942414LL, 1, "Failed to allocate class factory for service:%d", a1);
    }
  }
  else
  {
    v4 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "No class factory result specified");
  }
  return v4;
}

```

## disassembly

```asm
0x14000ce08  mov     [rsp+arg_0], rbx
0x14000ce0d  mov     [rsp+arg_8], rsi
0x14000ce12  push    rdi
0x14000ce13  sub     rsp, 30h
0x14000ce17  mov     rdi, rdx
0x14000ce1a  mov     esi, ecx
0x14000ce1c  test    rdx, rdx
0x14000ce1f  jnz     short loc_14000CE3F
0x14000ce21  lea     r8d, [rdx+1]
0x14000ce25  mov     ebx, 80004003h
0x14000ce2a  mov     edx, ebx
0x14000ce2c  lea     r9, aNoClassFactory; "No class factory result specified"
0x14000ce33  mov     ecx, 4000000h
0x14000ce38  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ce3d  jmp     short loc_14000CE9A
0x14000ce3f  mov     ecx, 38h ; '8'; Size
0x14000ce44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ce49  test    rax, rax
0x14000ce4c  jz      short loc_14000CE78
0x14000ce4e  mov     edx, esi; unsigned int
0x14000ce50  mov     rcx, rax; this
0x14000ce53  call    ??0CCbsPublicFacadeClassFactory@@QEAA@K@Z; CCbsPublicFacadeClassFactory::CCbsPublicFacadeClassFactory(ulong)
0x14000ce58  mov     rdx, rax
0x14000ce5b  test    rax, rax
0x14000ce5e  jz      short loc_14000CE78
0x14000ce60  mov     rax, [rax+8]
0x14000ce64  movsxd  rax, dword ptr [rax+4]
0x14000ce68  add     rax, 8
0x14000ce6c  add     rax, rdx
0x14000ce6f  jz      short loc_14000CE78
0x14000ce71  xor     ebx, ebx
0x14000ce73  mov     [rdi], rax
0x14000ce76  jmp     short loc_14000CE9A
0x14000ce78  mov     ebx, 8007000Eh
0x14000ce7d  mov     [rsp+38h+var_18], esi
0x14000ce81  mov     edx, ebx
0x14000ce83  lea     r9, aFailedToAlloca_15; "Failed to allocate class factory for se"...
0x14000ce8a  mov     r8d, 1
0x14000ce90  mov     ecx, 4000000h
0x14000ce95  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ce9a  mov     rsi, [rsp+38h+arg_8]
0x14000ce9f  mov     eax, ebx
0x14000cea1  mov     rbx, [rsp+38h+arg_0]
0x14000cea6  add     rsp, 30h
0x14000ceaa  pop     rdi
0x14000ceab  retn
```
