# winrt::hstring::hstring(wchar_t const *)

- ea: `0x1800013a0`
- end: `0x18000144c`
- name: `??0hstring@winrt@@QEAA@PEB_W@Z`
- size: `172`
- prototype: `winrt::hstring *__fastcall(winrt::hstring *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006490`

## callees

- `0x1800012f0`
- `0x1800013a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800013c3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800013c3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800013cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800013cf`

## string_xrefs

- `0x1800013e6`: `Microsoft.Windows.PrivateCommon.ImageBufferResource`

## pseudocode

```c
winrt::hstring *__fastcall winrt::hstring::hstring(winrt::hstring *this, const wchar_t *a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  winrt::hstring *result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x33, (unsigned int)a2);
  v4 = v3;
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    result = this;
    *(_QWORD *)this = -28;
  }
  else
  {
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Windows.PrivateCommon.ImageBufferResource";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Windows.PrivateCommon.ImageBufferResource";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"s.PrivateCommon.ImageBufferResource";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"eCommon.ImageBufferResource";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"ImageBufferResource";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"ferResource";
    *((_DWORD *)v3 + 31) = *(_DWORD *)L"rce";
    *((_WORD *)v3 + 64) = aMicrosoftWindo_0[50];
    result = this;
    *(_QWORD *)this = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800013a0  mov     [rsp+arg_0], rbx
0x1800013a5  push    rdi
0x1800013a6  sub     rsp, 20h
0x1800013aa  mov     rbx, rcx
0x1800013ad  mov     ecx, 33h ; '3'; this
0x1800013b2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800013b7  mov     rdi, rax
0x1800013ba  lea     rcx, [rax+1Ch]
0x1800013be  test    rcx, rcx
0x1800013c1  jnz     short loc_1800013E6
0x1800013c3  call    cs:__imp__errno
0x1800013c9  mov     dword ptr [rax], 16h
0x1800013cf  call    cs:__imp__invalid_parameter_noinfo
0x1800013d5  mov     rax, rbx
0x1800013d8  mov     [rbx], rdi
0x1800013db  mov     rbx, [rsp+28h+arg_0]
0x1800013e0  add     rsp, 20h
0x1800013e4  pop     rdi
0x1800013e5  retn
0x1800013e6  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_0; "Microsoft.Windows.PrivateCommon.ImageBu"...
0x1800013ed  movups  xmmword ptr [rcx], xmm0
0x1800013f0  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_0+10h; "t.Windows.PrivateCommon.ImageBufferReso"...
0x1800013f7  movups  xmmword ptr [rcx+10h], xmm1
0x1800013fb  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_0+20h; "s.PrivateCommon.ImageBufferResource"
0x180001402  movups  xmmword ptr [rcx+20h], xmm0
0x180001406  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_0+30h; "eCommon.ImageBufferResource"
0x18000140d  movups  xmmword ptr [rcx+30h], xmm1
0x180001411  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_0+40h; "ImageBufferResource"
0x180001418  movups  xmmword ptr [rcx+40h], xmm0
0x18000141c  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_0+50h; "ferResource"
0x180001423  movups  xmmword ptr [rcx+50h], xmm1
0x180001427  mov     eax, dword ptr cs:aMicrosoftWindo_0+60h; "rce"
0x18000142d  mov     [rcx+60h], eax
0x180001430  movzx   eax, word ptr cs:aMicrosoftWindo_0+64h; "e"
0x180001437  mov     [rcx+64h], ax
0x18000143b  mov     rax, rbx
0x18000143e  mov     [rbx], rdi
0x180001441  mov     rbx, [rsp+28h+arg_0]
0x180001446  add     rsp, 20h
0x18000144a  pop     rdi
0x18000144b  retn
```
