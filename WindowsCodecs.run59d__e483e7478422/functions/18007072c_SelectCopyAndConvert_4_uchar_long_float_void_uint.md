# SelectCopyAndConvert<4,uchar>(long (**)(float *,void *,uint))

- ea: `0x18007072c`
- end: `0x1800707dc`
- name: `??$SelectCopyAndConvert@$03E@@YAJPEAP6AJPEAMPEAXI@Z@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800707e4`

## callees

- `0x18007072c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180070751`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18007076b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180070785`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18007079b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180070751`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18007076b`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180070785`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18007079b`

## pseudocode

```c
__int64 __fastcall SelectCopyAndConvert<4,unsigned char>(__int64 (__fastcall **a1)())
{
  __int64 (__fastcall *v2)(); // rax

  *a1 = 0;
  if ( (unsigned int)__std_type_info_compare(&qword_180269498, &qword_1802694E0)
    && (unsigned int)__std_type_info_compare(&qword_180269498, &qword_1802694C8)
    && (unsigned int)__std_type_info_compare(&qword_180269498, &qword_1802694B0)
    && (unsigned int)__std_type_info_compare(&qword_180269498, &qword_180269498) )
  {
    return 2147500037LL;
  }
  v2 = CopyAndConvert_C<4,unsigned char>;
  if ( CCPUInfo::m_fHasSSE2 )
    v2 = CopyAndConvert_SSE2<4,unsigned char>;
  *a1 = v2;
  return 0;
}

```

## disassembly

```asm
0x18007072c  mov     [rsp+arg_0], rbx
0x180070731  push    rdi
0x180070732  sub     rsp, 20h
0x180070736  mov     rbx, rcx
0x180070739  mov     qword ptr [rcx], 0
0x180070740  lea     rdi, qword_180269498
0x180070747  mov     rcx, rdi
0x18007074a  lea     rdx, qword_1802694E0
0x180070751  call    cs:__imp___std_type_info_compare
0x180070758  nop     dword ptr [rax+rax+00h]
0x18007075d  test    eax, eax
0x18007075f  jz      short loc_1800707AB
0x180070761  lea     rdx, qword_1802694C8
0x180070768  mov     rcx, rdi
0x18007076b  call    cs:__imp___std_type_info_compare
0x180070772  nop     dword ptr [rax+rax+00h]
0x180070777  test    eax, eax
0x180070779  jz      short loc_1800707AB
0x18007077b  lea     rdx, qword_1802694B0
0x180070782  mov     rcx, rdi
0x180070785  call    cs:__imp___std_type_info_compare
0x18007078c  nop     dword ptr [rax+rax+00h]
0x180070791  test    eax, eax
0x180070793  jz      short loc_1800707AB
0x180070795  mov     rdx, rdi
0x180070798  mov     rcx, rdi
0x18007079b  call    cs:__imp___std_type_info_compare
0x1800707a2  nop     dword ptr [rax+rax+00h]
0x1800707a7  test    eax, eax
0x1800707a9  jnz     short loc_1800707D5
0x1800707ab  cmp     cs:?m_fHasSSE2@CCPUInfo@@0_NA, 0; bool CCPUInfo::m_fHasSSE2
0x1800707b2  lea     rax, ??$CopyAndConvert_C@$03E@@YAJPEAMPEAXI@Z; CopyAndConvert_C<4,uchar>(float *,void *,uint)
0x1800707b9  lea     rcx, ??$CopyAndConvert_SSE2@$03E@@YAJPEAMPEAXI@Z; CopyAndConvert_SSE2<4,uchar>(float *,void *,uint)
0x1800707c0  cmovnz  rax, rcx
0x1800707c4  mov     [rbx], rax
0x1800707c7  xor     eax, eax
0x1800707c9  mov     rbx, [rsp+28h+arg_0]
0x1800707ce  add     rsp, 20h
0x1800707d2  pop     rdi
0x1800707d3  retn
0x1800707d5  mov     eax, 80004005h
0x1800707da  jmp     short loc_1800707C9
```
