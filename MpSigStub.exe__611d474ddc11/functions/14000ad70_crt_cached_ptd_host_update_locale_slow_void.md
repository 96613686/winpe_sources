# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x14000ad70`
- end: `0x14000ade6`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `17`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400065ac`
- `0x14000d360`
- `0x14000d6dc`
- `0x14000e470`
- `0x14000e9ec`
- `0x14000ec40`
- `0x14000ef7c`
- `0x14000f230`
- `0x140010800`
- `0x140010af0`
- `0x1400113dc`
- `0x1400115ec`
- `0x1400120a0`
- `0x14001253c`
- `0x1400127f8`
- `0x1400191f8`
- `0x140019bc8`

## callees

- `0x1400042e0`
- `0x14000ad70`
- `0x1400102d8`
- `0x140010344`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  __int64 v2; // rsi
  int v3; // eax

  v2 = unknown_libname_44();
  *((_QWORD *)this + 3) = *(_QWORD *)(v2 + 144);
  *((_QWORD *)this + 4) = *(_QWORD *)(v2 + 136);
  sub_1400102D8(v2, (char *)this + 24, *((_QWORD *)this + 1));
  sub_140010344(v2, (char *)this + 32, *((_QWORD *)this + 1));
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
0x14000ad70  mov     [rsp+arg_0], rbx
0x14000ad75  mov     [rsp+arg_8], rsi
0x14000ad7a  push    rdi
0x14000ad7b  sub     rsp, 20h
0x14000ad7f  mov     rdi, rcx
0x14000ad82  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000ad87  lea     rdx, [rdi+18h]
0x14000ad8b  mov     rcx, rax
0x14000ad8e  mov     rsi, rax
0x14000ad91  mov     r8, [rax+90h]
0x14000ad98  mov     [rdx], r8
0x14000ad9b  mov     r8, [rax+88h]
0x14000ada2  mov     [rdi+20h], r8
0x14000ada6  mov     r8, [rdi+8]
0x14000adaa  call    sub_1400102D8
0x14000adaf  mov     r8, [rdi+8]
0x14000adb3  lea     rdx, [rdi+20h]
0x14000adb7  mov     rcx, rsi
0x14000adba  call    sub_140010344
0x14000adbf  mov     eax, [rsi+3A8h]
0x14000adc5  test    al, 2
0x14000adc7  jnz     short loc_14000ADD6
0x14000adc9  or      eax, 2
0x14000adcc  mov     [rsi+3A8h], eax
0x14000add2  mov     byte ptr [rdi+28h], 2
0x14000add6  mov     rbx, [rsp+28h+arg_0]
0x14000addb  mov     rsi, [rsp+28h+arg_8]
0x14000ade0  add     rsp, 20h
0x14000ade4  pop     rdi
0x14000ade5  retn
```
