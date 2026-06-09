# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,double)

- ea: `0x1400036e8`
- end: `0x140003837`
- name: `??$AddColumnToCoalescedEvent@N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGN@Z`
- size: `335`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *, __int64 **, const WCHAR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000365c`
- `0x14000732c`
- `0x14000a3b0`

## callees

- `0x140002600`
- `0x1400036e8`
- `0x140005ea0`
- `0x140007870`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400037a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400037a4`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(
        Windows::Speech::Session::FlightDataRecorder *a1,
        __int64 **a2,
        const WCHAR *a3)
{
  int v6; // ebx
  unsigned int v7; // r8d
  __int64 *v8; // rbx
  __int64 v9; // r14
  unsigned __int64 v10; // rdx
  __int64 v11; // rbp
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rcx
  __int64 *v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string; // [rsp+48h] [rbp-60h] BYREF

  v18[1] = a2;
  if ( *a2 && a3 )
    v6 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(a1);
  else
    v6 = -2147024809;
  v18[0] = 0;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **, _QWORD *))(**((_QWORD **)a1 + 10) + 72LL))(
           *((_QWORD **)a1 + 10),
           a2,
           v18);
    if ( v6 >= 0 )
    {
      v8 = *a2;
      v9 = **a2;
      string = 0;
      v10 = -1;
      do
        ++v10;
      while ( a3[v10] );
      if ( v10 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v7);
        __debugbreak();
      }
      if ( (int)v10 + 1 < (unsigned int)v10 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v7);
        JUMPOUT(0x140003836LL);
      }
      v11 = v18[0];
      v12 = WindowsCreateStringReference(a3, v10, &hstringHeader, &string);
      if ( v12 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
        __debugbreak();
      }
      v6 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64))(v9 + 56))(v8, string, v11);
    }
  }
  v15 = v18[0];
  if ( v18[0] )
  {
    v18[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400036e8  push    rbx
0x1400036ea  push    rbp
0x1400036eb  push    rsi
0x1400036ec  push    rdi
0x1400036ed  push    r14
0x1400036ef  push    r15
0x1400036f1  sub     rsp, 78h
0x1400036f5  movaps  [rsp+0A8h+var_48], xmm6
0x1400036fa  mov     rax, cs:__security_cookie
0x140003701  xor     rax, rsp
0x140003704  mov     [rsp+0A8h+var_58], rax
0x140003709  movaps  xmm6, xmm3
0x14000370c  mov     rsi, r8
0x14000370f  mov     rdi, rdx
0x140003712  mov     rbp, rcx
0x140003715  mov     [rsp+0A8h+var_80], rdx
0x14000371a  xor     r15d, r15d
0x14000371d  cmp     [rdx], r15
0x140003720  jz      short loc_140003730
0x140003722  test    r8, r8
0x140003725  jz      short loc_140003730
0x140003727  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000372c  mov     ebx, eax
0x14000372e  jmp     short loc_140003735
0x140003730  mov     ebx, 80070057h
0x140003735  mov     [rsp+0A8h+var_88], r15
0x14000373a  test    ebx, ebx
0x14000373c  js      loc_1400037C4
0x140003742  mov     rcx, [rbp+50h]
0x140003746  mov     rax, [rcx]
0x140003749  lea     r8, [rsp+0A8h+var_88]
0x14000374e  movaps  xmm1, xmm6
0x140003751  mov     rax, [rax+48h]
0x140003755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000375a  mov     ebx, eax
0x14000375c  test    eax, eax
0x14000375e  js      short loc_1400037C4
0x140003760  mov     rbx, [rdi]
0x140003763  mov     r14, [rbx]
0x140003766  mov     [rsp+0A8h+string], r15
0x14000376b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000376f  inc     rdx; int
0x140003772  cmp     [rsi+rdx*2], r15w
0x140003777  jnz     short loc_14000376F
0x140003779  mov     eax, 0FFFFFFFFh
0x14000377e  cmp     rdx, rax
0x140003781  ja      loc_140003821
0x140003787  lea     eax, [rdx+1]
0x14000378a  cmp     eax, edx
0x14000378c  jb      loc_14000382C
0x140003792  mov     rbp, [rsp+0A8h+var_88]
0x140003797  lea     r9, [rsp+0A8h+string]; string
0x14000379c  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400037a1  mov     rcx, rsi; sourceString
0x1400037a4  call    cs:__imp_WindowsCreateStringReference
0x1400037aa  test    eax, eax
0x1400037ac  js      short loc_140003819
0x1400037ae  mov     r8, rbp
0x1400037b1  mov     rdx, [rsp+0A8h+string]
0x1400037b6  mov     rcx, rbx
0x1400037b9  mov     rax, [r14+38h]
0x1400037bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037c2  mov     ebx, eax
0x1400037c4  mov     rcx, [rsp+0A8h+var_88]
0x1400037c9  test    rcx, rcx
0x1400037cc  jz      short loc_1400037E0
0x1400037ce  mov     [rsp+0A8h+var_88], r15
0x1400037d3  mov     rax, [rcx]
0x1400037d6  mov     rax, [rax+10h]
0x1400037da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037df  nop
0x1400037e0  mov     rcx, [rdi]
0x1400037e3  test    rcx, rcx
0x1400037e6  jz      short loc_1400037F8
0x1400037e8  mov     [rdi], r15
0x1400037eb  mov     rax, [rcx]
0x1400037ee  mov     rax, [rax+10h]
0x1400037f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037f7  nop
0x1400037f8  mov     eax, ebx
0x1400037fa  mov     rcx, [rsp+0A8h+var_58]
0x1400037ff  xor     rcx, rsp; StackCookie
0x140003802  call    __security_check_cookie
0x140003807  movaps  xmm6, [rsp+0A8h+var_48]
0x14000380c  add     rsp, 78h
0x140003810  pop     r15
0x140003812  pop     r14
0x140003814  pop     rdi
0x140003815  pop     rsi
0x140003816  pop     rbp
0x140003817  pop     rbx
0x140003818  retn
0x140003819  mov     ecx, eax; this
0x14000381b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140003820  int     3; Trap to Debugger
0x140003821  mov     ecx, 80070216h; this
0x140003826  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000382b  int     3; Trap to Debugger
0x14000382c  mov     ecx, 80070216h; this
0x140003831  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
