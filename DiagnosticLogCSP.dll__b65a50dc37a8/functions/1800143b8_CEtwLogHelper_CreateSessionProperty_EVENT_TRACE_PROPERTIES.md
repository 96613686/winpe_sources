# CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)

- ea: `0x1800143b8`
- end: `0x180014414`
- name: `?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800144bc`
- `0x1800146e4`
- `0x1800148f0`
- `0x180014ab4`

## callees

- `0x1800143b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143c6`

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
0x1800143b8  push    rbx
0x1800143ba  sub     rsp, 20h
0x1800143be  mov     rbx, rcx
0x1800143c1  mov     ecx, 107Ch; cb
0x1800143c6  call    cs:__imp_CoTaskMemAlloc
0x1800143cd  nop     dword ptr [rax+rax+00h]
0x1800143d2  test    rax, rax
0x1800143d5  jnz     short loc_1800143DE
0x1800143d7  mov     ecx, 8007000Eh
0x1800143dc  jmp     short loc_18001440B
0x1800143de  xor     ecx, ecx
0x1800143e0  mov     r8d, 107Ch
0x1800143e6  mov     rdx, rax
0x1800143e9  mov     [rdx], cl
0x1800143eb  inc     rdx
0x1800143ee  sub     r8, 1
0x1800143f2  jnz     short loc_1800143E9
0x1800143f4  mov     dword ptr [rax], 107Ch
0x1800143fa  mov     dword ptr [rax+74h], 78h ; 'x'
0x180014401  mov     dword ptr [rax+70h], 87Ah
0x180014408  mov     [rbx], rax
0x18001440b  mov     eax, ecx
0x18001440d  add     rsp, 20h
0x180014411  pop     rbx
0x180014412  retn
```
