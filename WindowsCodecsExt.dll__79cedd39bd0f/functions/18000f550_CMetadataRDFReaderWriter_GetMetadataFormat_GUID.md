# CMetadataRDFReaderWriter::GetMetadataFormat(_GUID *)

- ea: `0x18000f550`
- end: `0x18000f5e1`
- name: `?GetMetadataFormat@CMetadataRDFReaderWriter@@UEAAJPEAU_GUID@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f550`
- `0x1800171c4`
- `0x180022644`
- `0x180022650`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetMetadataFormat(CMetadataRDFReaderWriter *this, struct _GUID *a2)
{
  char *v2; // rbx
  unsigned int v5; // r14d

  v2 = (char *)this + 40;
  if ( *((_BYTE *)this + 88) )
    EnterCriticalSection_0((LPCRITICAL_SECTION)((char *)this + 48));
  if ( a2 )
  {
    v5 = 0;
    *a2 = *(struct _GUID *)*((_QWORD *)this + 19);
  }
  else
  {
    v5 = -2147024809;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  if ( v2 && v2[48] )
    LeaveCriticalSection_0((LPCRITICAL_SECTION)(v2 + 8));
  return v5;
}

```

## disassembly

```asm
0x18000f550  mov     [rsp+arg_18], rbx
0x18000f555  push    rdi
0x18000f556  sub     rsp, 20h
0x18000f55a  cmp     byte ptr [rcx+58h], 0
0x18000f55e  lea     rbx, [rcx+28h]
0x18000f562  mov     [rsp+28h+arg_0], rbp
0x18000f567  mov     rbp, rcx
0x18000f56a  mov     [rsp+28h+arg_8], rsi
0x18000f56f  mov     rsi, rdx
0x18000f572  jz      short loc_18000F57D
0x18000f574  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f578  call    EnterCriticalSection_0
0x18000f57d  mov     [rsp+28h+arg_10], r14
0x18000f582  test    rsi, rsi
0x18000f585  jz      short loc_18000F5C8
0x18000f587  mov     rdx, [rbp+98h]
0x18000f58e  xor     r14d, r14d
0x18000f591  movups  xmm0, xmmword ptr [rdx]
0x18000f594  movups  xmmword ptr [rsi], xmm0
0x18000f597  mov     rsi, [rsp+28h+arg_8]
0x18000f59c  mov     rbp, [rsp+28h+arg_0]
0x18000f5a1  test    rbx, rbx
0x18000f5a4  jz      short loc_18000F5B5
0x18000f5a6  cmp     byte ptr [rbx+30h], 0
0x18000f5aa  jz      short loc_18000F5B5
0x18000f5ac  lea     rcx, [rbx+8]; lpCriticalSection
0x18000f5b0  call    LeaveCriticalSection_0
0x18000f5b5  mov     rbx, [rsp+28h+arg_18]
0x18000f5ba  mov     eax, r14d
0x18000f5bd  mov     r14, [rsp+28h+arg_10]
0x18000f5c2  add     rsp, 20h
0x18000f5c6  pop     rdi
0x18000f5c7  retn
0x18000f5c8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f5cf  mov     r14d, 80070057h
0x18000f5d5  jz      short loc_18000F597
0x18000f5d7  mov     ecx, r14d; int
0x18000f5da  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f5df  jmp     short loc_18000F597
```
