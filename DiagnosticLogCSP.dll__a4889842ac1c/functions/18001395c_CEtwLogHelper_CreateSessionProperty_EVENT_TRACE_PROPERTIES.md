# CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)

- ea: `0x18001395c`
- end: `0x1800139b1`
- name: `?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013a4c`
- `0x180013c54`
- `0x180013e4c`
- `0x180014004`

## callees

- `0x18001395c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001396a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001396a`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::CreateSessionProperty(struct _EVENT_TRACE_PROPERTIES **a1)
{
  struct _EVENT_TRACE_PROPERTIES *v2; // rax
  unsigned int v3; // ecx
  __int64 v4; // r8
  struct _EVENT_TRACE_PROPERTIES *v5; // rdx

  v2 = (struct _EVENT_TRACE_PROPERTIES *)CoTaskMemAlloc(0x107Cu);
  if ( v2 )
  {
    v3 = 0;
    v4 = 4220;
    v5 = v2;
    do
    {
      LOBYTE(v5->Wnode.BufferSize) = 0;
      v5 = (struct _EVENT_TRACE_PROPERTIES *)((char *)v5 + 1);
      --v4;
    }
    while ( v4 );
    v2->Wnode.BufferSize = 4220;
    v2->LoggerNameOffset = 120;
    v2->LogFileNameOffset = 2170;
    *a1 = v2;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x18001395c  push    rbx
0x18001395e  sub     rsp, 20h
0x180013962  mov     rbx, rcx
0x180013965  mov     ecx, 107Ch; cb
0x18001396a  call    cs:__imp_CoTaskMemAlloc
0x180013970  test    rax, rax
0x180013973  jnz     short loc_18001397C
0x180013975  mov     ecx, 8007000Eh
0x18001397a  jmp     short loc_1800139A9
0x18001397c  xor     ecx, ecx
0x18001397e  mov     r8d, 107Ch
0x180013984  mov     rdx, rax
0x180013987  mov     [rdx], cl
0x180013989  inc     rdx
0x18001398c  sub     r8, 1
0x180013990  jnz     short loc_180013987
0x180013992  mov     dword ptr [rax], 107Ch
0x180013998  mov     dword ptr [rax+74h], 78h ; 'x'
0x18001399f  mov     dword ptr [rax+70h], 87Ah
0x1800139a6  mov     [rbx], rax
0x1800139a9  mov     eax, ecx
0x1800139ab  add     rsp, 20h
0x1800139af  pop     rbx
0x1800139b0  retn
```
