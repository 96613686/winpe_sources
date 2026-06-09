# SelectCopyAndConvert<4,uchar>(long (**)(float *,void *,uint))

- ea: `0x18002b8e8`
- end: `0x18002b97f`
- name: `??$SelectCopyAndConvert@$03E@@YAJPEAP6AJPEAMPEAXI@Z@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002b988`

## callees

- `0x18002b8e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b90d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b921`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b935`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b945`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b90d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b921`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b935`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002b945`

## pseudocode

```c
__int64 __fastcall SelectCopyAndConvert<4,unsigned char>(__int64 (__fastcall **a1)())
{
  __int64 (__fastcall *v2)(); // rax

  *a1 = 0;
  if ( (unsigned int)__std_type_info_compare(&qword_180265388, &qword_1802653D0)
    && (unsigned int)__std_type_info_compare(&qword_180265388, &qword_1802653B8)
    && (unsigned int)__std_type_info_compare(&qword_180265388, &qword_1802653A0)
    && (unsigned int)__std_type_info_compare(&qword_180265388, &qword_180265388) )
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
0x18002b8e8  mov     [rsp+arg_0], rbx
0x18002b8ed  push    rdi
0x18002b8ee  sub     rsp, 20h
0x18002b8f2  mov     rbx, rcx
0x18002b8f5  mov     qword ptr [rcx], 0
0x18002b8fc  lea     rdi, qword_180265388
0x18002b903  mov     rcx, rdi
0x18002b906  lea     rdx, qword_1802653D0
0x18002b90d  call    cs:__imp___std_type_info_compare
0x18002b913  test    eax, eax
0x18002b915  jz      short loc_18002B94F
0x18002b917  lea     rdx, qword_1802653B8
0x18002b91e  mov     rcx, rdi
0x18002b921  call    cs:__imp___std_type_info_compare
0x18002b927  test    eax, eax
0x18002b929  jz      short loc_18002B94F
0x18002b92b  lea     rdx, qword_1802653A0
0x18002b932  mov     rcx, rdi
0x18002b935  call    cs:__imp___std_type_info_compare
0x18002b93b  test    eax, eax
0x18002b93d  jz      short loc_18002B94F
0x18002b93f  mov     rdx, rdi
0x18002b942  mov     rcx, rdi
0x18002b945  call    cs:__imp___std_type_info_compare
0x18002b94b  test    eax, eax
0x18002b94d  jnz     short loc_18002B978
0x18002b94f  cmp     cs:?m_fHasSSE2@CCPUInfo@@0_NA, 0; bool CCPUInfo::m_fHasSSE2
0x18002b956  lea     rax, ??$CopyAndConvert_C@$03E@@YAJPEAMPEAXI@Z; CopyAndConvert_C<4,uchar>(float *,void *,uint)
0x18002b95d  lea     rcx, ??$CopyAndConvert_SSE2@$03E@@YAJPEAMPEAXI@Z; CopyAndConvert_SSE2<4,uchar>(float *,void *,uint)
0x18002b964  cmovnz  rax, rcx
0x18002b968  mov     [rbx], rax
0x18002b96b  xor     eax, eax
0x18002b96d  mov     rbx, [rsp+28h+arg_0]
0x18002b972  add     rsp, 20h
0x18002b976  pop     rdi
0x18002b977  retn
0x18002b978  mov     eax, 80004005h
0x18002b97d  jmp     short loc_18002B96D
```
