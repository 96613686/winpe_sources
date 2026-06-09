# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x140065e50`
- end: `0x140065ec6`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `19`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140063ac4`
- `0x140063e2c`
- `0x140064a54`
- `0x140064ec4`
- `0x14006552c`
- `0x140065788`
- `0x140065ad8`
- `0x140065d8c`
- `0x14006b990`
- `0x14006bc6c`
- `0x140072418`
- `0x1400728b0`
- `0x140072b6c`
- `0x140073210`
- `0x1400733c0`
- `0x1400763a8`
- `0x140076cf4`
- `0x14007a1e0`
- `0x14007a594`

## callees

- `0x140061148`
- `0x140065e50`
- `0x140072374`
- `0x1400723e0`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  __int64 v2; // rsi
  int v3; // eax

  v2 = unknown_libname_67();
  *((_QWORD *)this + 3) = *(_QWORD *)(v2 + 144);
  *((_QWORD *)this + 4) = *(_QWORD *)(v2 + 136);
  sub_140072374(v2, (char *)this + 24, *((_QWORD *)this + 1));
  sub_1400723E0(v2, (char *)this + 32, *((_QWORD *)this + 1));
  v3 = *(_DWORD *)(v2 + 936);
  if ( (v3 & 2) == 0 )
  {
    *(_DWORD *)(v2 + 936) = v3 | 2;
    *((_BYTE *)this + 40) = 2;
  }
}

```

## disassembly

```asm
0x140065e50  mov     [rsp+arg_0], rbx
0x140065e55  mov     [rsp+arg_8], rsi
0x140065e5a  push    rdi
0x140065e5b  sub     rsp, 20h
0x140065e5f  mov     rdi, rcx
0x140065e62  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x140065e67  lea     rdx, [rdi+18h]
0x140065e6b  mov     rcx, rax
0x140065e6e  mov     rsi, rax
0x140065e71  mov     r8, [rax+90h]
0x140065e78  mov     [rdx], r8
0x140065e7b  mov     r8, [rax+88h]
0x140065e82  mov     [rdi+20h], r8
0x140065e86  mov     r8, [rdi+8]
0x140065e8a  call    sub_140072374
0x140065e8f  mov     r8, [rdi+8]
0x140065e93  lea     rdx, [rdi+20h]
0x140065e97  mov     rcx, rsi
0x140065e9a  call    sub_1400723E0
0x140065e9f  mov     eax, [rsi+3A8h]
0x140065ea5  test    al, 2
0x140065ea7  jnz     short loc_140065EB6
0x140065ea9  or      eax, 2
0x140065eac  mov     [rsi+3A8h], eax
0x140065eb2  mov     byte ptr [rdi+28h], 2
0x140065eb6  mov     rbx, [rsp+28h+arg_0]
0x140065ebb  mov     rsi, [rsp+28h+arg_8]
0x140065ec0  add     rsp, 20h
0x140065ec4  pop     rdi
0x140065ec5  retn
```
