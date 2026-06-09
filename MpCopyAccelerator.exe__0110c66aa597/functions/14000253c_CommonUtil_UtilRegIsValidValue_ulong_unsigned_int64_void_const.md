# CommonUtil::UtilRegIsValidValue(ulong,unsigned __int64,void const *)

- ea: `0x14000253c`
- end: `0x140002582`
- name: `?UtilRegIsValidValue@CommonUtil@@YA_NK_KPEBX@Z`
- size: `70`
- prototype: `bool __fastcall(CommonUtil *__hidden this, unsigned int, unsigned __int64, const void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005050`

## callees

- `0x140002d42`
- `0x140024c40`

## pseudocode

```c
bool __fastcall CommonUtil::UtilRegIsValidValue(CommonUtil *this, __int64 a2, __int64 a3, const void *a4)
{
  unsigned int v6; // esi
  __int64 v7; // rax

  v6 = (unsigned int)this;
  v7 = MpUtilsExportFunctions_0(this, a2);
  return (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(v7 + 248))(v6, a2, a3) != 0;
}

```

## disassembly

```asm
0x14000253c  mov     [rsp+arg_0], rbx
0x140002541  mov     [rsp+arg_8], rsi
0x140002546  push    rdi
0x140002547  sub     rsp, 20h
0x14000254b  mov     rbx, r8
0x14000254e  mov     rdi, rdx
0x140002551  mov     esi, ecx
0x140002553  call    MpUtilsExportFunctions_0
0x140002558  mov     r8, rbx
0x14000255b  mov     rdx, rdi
0x14000255e  mov     ecx, esi
0x140002560  mov     rax, [rax+0F8h]
0x140002567  call    cs:__guard_dispatch_icall_fptr
0x14000256d  test    eax, eax
0x14000256f  setnz   al
0x140002572  mov     rbx, [rsp+28h+arg_0]
0x140002577  mov     rsi, [rsp+28h+arg_8]
0x14000257c  add     rsp, 20h
0x140002580  pop     rdi
0x140002581  retn
```
