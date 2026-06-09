# MdmHttpRequest::SendRequestToCommandService(ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001c5f0`
- end: `0x18001c6ec`
- name: `?SendRequestToCommandService@MdmHttpRequest@@UEAAJPEBG000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `252`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWCH, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de4`
- `0x180012e38`
- `0x18001c298`
- `0x18001c5f0`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SendRequestToCommandService(
        MdmHttpRequest *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWCH lpWideCharStr,
        unsigned int *a7,
        __int64 a8)
{
  int ServiceHost; // ebx
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v15[2]; // [rsp+58h] [rbp-70h] BYREF
  __m128i si128; // [rsp+68h] [rbp-60h]

  *(_OWORD *)v15 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v15[0]) = 0;
  ServiceHost = MdmSettings::GetServiceHost(v15);
  if ( ServiceHost >= 0 )
  {
    if ( si128.m128i_i64[0] )
    {
      v13 = (unsigned __int16 *)v15;
      if ( si128.m128i_i64[1] > 7uLL )
        v13 = v15[0];
      ServiceHost = MdmHttpRequest::SendRequest(this, v13, a2, a3, a4, a5, lpWideCharStr, a7, a8);
    }
    else
    {
      ServiceHost = -2147418113;
    }
  }
  std::wstring::~wstring(v15);
  return (unsigned int)ServiceHost;
}

```

## disassembly

```asm
0x18001c5f0  push    rbx
0x18001c5f2  push    rbp
0x18001c5f3  push    rsi
0x18001c5f4  push    rdi
0x18001c5f5  push    r12
0x18001c5f7  push    r13
0x18001c5f9  push    r14
0x18001c5fb  push    r15
0x18001c5fd  sub     rsp, 88h
0x18001c604  mov     rax, cs:__security_cookie
0x18001c60b  xor     rax, rsp
0x18001c60e  mov     [rsp+0C8h+var_50], rax
0x18001c613  mov     r14, r9
0x18001c616  mov     rbp, r8
0x18001c619  mov     rsi, rdx
0x18001c61c  mov     rdi, rcx
0x18001c61f  mov     r15, [rsp+0C8h+arg_20]
0x18001c627  mov     r12, [rsp+0C8h+arg_28]
0x18001c62f  mov     r13, [rsp+0C8h+arg_30]
0x18001c637  mov     rax, [rsp+0C8h+arg_38]
0x18001c63f  mov     [rsp+0C8h+var_78], rax
0x18001c644  xorps   xmm0, xmm0
0x18001c647  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x18001c64c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c654  movdqu  [rsp+0C8h+var_60], xmm1
0x18001c65a  xor     eax, eax
0x18001c65c  mov     word ptr [rsp+0C8h+var_70], ax
0x18001c661  lea     rcx, [rsp+0C8h+var_70]
0x18001c666  call    ?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetServiceHost(std::wstring &)
0x18001c66b  mov     ebx, eax
0x18001c66d  test    eax, eax
0x18001c66f  js      short loc_18001C6BF
0x18001c671  cmp     qword ptr [rsp+0C8h+var_60], 0
0x18001c677  jnz     short loc_18001C680
0x18001c679  mov     ebx, 8000FFFFh
0x18001c67e  jmp     short loc_18001C6BF
0x18001c680  lea     rdx, [rsp+0C8h+var_70]
0x18001c685  cmp     qword ptr [rsp+0C8h+var_60+8], 7
0x18001c68b  cmova   rdx, [rsp+0C8h+var_70]; unsigned __int16 *
0x18001c691  mov     rax, [rsp+0C8h+var_78]
0x18001c696  mov     [rsp+0C8h+var_88], rax; __int64
0x18001c69b  mov     [rsp+0C8h+var_90], r13; unsigned int *
0x18001c6a0  mov     [rsp+0C8h+lpWideCharStr], r12; lpWideCharStr
0x18001c6a5  mov     [rsp+0C8h+var_A0], r15; unsigned __int16 *
0x18001c6aa  mov     [rsp+0C8h+var_A8], r14; unsigned __int16 *
0x18001c6af  mov     r9, rbp; unsigned __int16 *
0x18001c6b2  mov     r8, rsi; unsigned __int16 *
0x18001c6b5  mov     rcx, rdi; this
0x18001c6b8  call    ?SendRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z; MdmHttpRequest::SendRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::wstring &,ulong *,ushort * *)
0x18001c6bd  mov     ebx, eax
0x18001c6bf  lea     rcx, [rsp+0C8h+var_70]
0x18001c6c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c6c9  mov     eax, ebx
0x18001c6cb  mov     rcx, [rsp+0C8h+var_50]
0x18001c6d0  xor     rcx, rsp; StackCookie
0x18001c6d3  call    __security_check_cookie
0x18001c6d8  add     rsp, 88h
0x18001c6df  pop     r15
0x18001c6e1  pop     r14
0x18001c6e3  pop     r13
0x18001c6e5  pop     r12
0x18001c6e7  pop     rdi
0x18001c6e8  pop     rsi
0x18001c6e9  pop     rbp
0x18001c6ea  pop     rbx
0x18001c6eb  retn
```
