# CommonUtil::UtilGetFileVersionInfoSize(ulong,wchar_t const *,ulong *,ulong *)

- ea: `0x140005630`
- end: `0x14000567c`
- name: `?UtilGetFileVersionInfoSize@CommonUtil@@YAJKPEB_WPEAK1@Z`
- size: `76`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int, const wchar_t *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000355c`

## callees

- `0x14000493c`
- `0x140005630`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFileVersionInfoSize(
        CommonUtil *this,
        __int64 a2,
        const wchar_t *a3,
        unsigned int *a4)
{
  __int64 v5; // rcx
  unsigned int v6; // edi
  unsigned int v7; // ebx
  __int64 result; // rax

  v6 = off_14003B128(this, a2, a3);
  v7 = 0;
  if ( v6 )
    result = 0;
  else
    result = HrGetLastFailure(v5);
  if ( (int)result >= 0 )
    v7 = v6;
  *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x140005630  mov     [rsp+arg_0], rbx
0x140005635  mov     [rsp+arg_8], rsi
0x14000563a  push    rdi
0x14000563b  sub     rsp, 20h
0x14000563f  mov     rsi, r9
0x140005642  mov     rax, cs:off_14003B128
0x140005649  call    cs:__guard_dispatch_icall_fptr
0x14000564f  mov     edi, eax
0x140005651  xor     ebx, ebx
0x140005653  test    eax, eax
0x140005655  jz      short loc_14000565B
0x140005657  mov     eax, ebx
0x140005659  jmp     short loc_140005660
0x14000565b  call    HrGetLastFailure
0x140005660  mov     ecx, eax
0x140005662  shr     ecx, 1Fh
0x140005665  test    cl, cl
0x140005667  cmovz   ebx, edi
0x14000566a  mov     [rsi], ebx
0x14000566c  mov     rbx, [rsp+28h+arg_0]
0x140005671  mov     rsi, [rsp+28h+arg_8]
0x140005676  add     rsp, 20h
0x14000567a  pop     rdi
0x14000567b  retn
```
