# MdmHttpRequest::SendRequestToCommandService(ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001cc30`
- end: `0x18001cd2d`
- name: `?SendRequestToCommandService@MdmHttpRequest@@UEAAJPEBG000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `253`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWCH, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de8`
- `0x18001321c`
- `0x18001c8d0`
- `0x18001cc30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MdmHttpRequest::SendRequestToCommandService(
        MdmHttpRequest *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWCH lpWideCharStr,
        unsigned int *a7,
        unsigned __int16 **a8)
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
0x18001cc30  push    rbx
0x18001cc32  push    rbp
0x18001cc33  push    rsi
0x18001cc34  push    rdi
0x18001cc35  push    r12
0x18001cc37  push    r13
0x18001cc39  push    r14
0x18001cc3b  push    r15
0x18001cc3d  sub     rsp, 88h
0x18001cc44  mov     rax, cs:__security_cookie
0x18001cc4b  xor     rax, rsp
0x18001cc4e  mov     [rsp+0C8h+var_50], rax
0x18001cc53  mov     r14, r9
0x18001cc56  mov     rbp, r8
0x18001cc59  mov     rsi, rdx
0x18001cc5c  mov     rdi, rcx
0x18001cc5f  mov     r15, [rsp+0C8h+arg_20]
0x18001cc67  mov     r12, [rsp+0C8h+arg_28]
0x18001cc6f  mov     r13, [rsp+0C8h+arg_30]
0x18001cc77  mov     rax, [rsp+0C8h+arg_38]
0x18001cc7f  mov     [rsp+0C8h+var_78], rax
0x18001cc84  xorps   xmm0, xmm0
0x18001cc87  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x18001cc8c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001cc94  movdqu  [rsp+0C8h+var_60], xmm1
0x18001cc9a  xor     eax, eax
0x18001cc9c  mov     word ptr [rsp+0C8h+var_70], ax
0x18001cca1  lea     rcx, [rsp+0C8h+var_70]
0x18001cca6  call    ?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetServiceHost(std::wstring &)
0x18001ccab  mov     ebx, eax
0x18001ccad  test    eax, eax
0x18001ccaf  js      short loc_18001CCFF
0x18001ccb1  cmp     qword ptr [rsp+0C8h+var_60], 0
0x18001ccb7  jnz     short loc_18001CCC0
0x18001ccb9  mov     ebx, 8000FFFFh
0x18001ccbe  jmp     short loc_18001CCFF
0x18001ccc0  lea     rdx, [rsp+0C8h+var_70]
0x18001ccc5  cmp     qword ptr [rsp+0C8h+var_60+8], 7
0x18001cccb  cmova   rdx, [rsp+0C8h+var_70]; unsigned __int16 *
0x18001ccd1  mov     rax, [rsp+0C8h+var_78]
0x18001ccd6  mov     [rsp+0C8h+var_88], rax; __int64
0x18001ccdb  mov     [rsp+0C8h+var_90], r13; unsigned int *
0x18001cce0  mov     [rsp+0C8h+lpWideCharStr], r12; lpWideCharStr
0x18001cce5  mov     [rsp+0C8h+var_A0], r15; unsigned __int16 *
0x18001ccea  mov     [rsp+0C8h+var_A8], r14; unsigned __int16 *
0x18001ccef  mov     r9, rbp; unsigned __int16 *
0x18001ccf2  mov     r8, rsi; unsigned __int16 *
0x18001ccf5  mov     rcx, rdi; this
0x18001ccf8  call    ?SendRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z; MdmHttpRequest::SendRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::wstring &,ulong *,ushort * *)
0x18001ccfd  mov     ebx, eax
0x18001ccff  lea     rcx, [rsp+0C8h+var_70]
0x18001cd04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cd09  mov     eax, ebx
0x18001cd0b  mov     rcx, [rsp+0C8h+var_50]
0x18001cd10  xor     rcx, rsp; StackCookie
0x18001cd13  call    __security_check_cookie
0x18001cd18  add     rsp, 88h
0x18001cd1f  pop     r15
0x18001cd21  pop     r14
0x18001cd23  pop     r13
0x18001cd25  pop     r12
0x18001cd27  pop     rdi
0x18001cd28  pop     rsi
0x18001cd29  pop     rbp
0x18001cd2a  pop     rbx
0x18001cd2b  retn
```
