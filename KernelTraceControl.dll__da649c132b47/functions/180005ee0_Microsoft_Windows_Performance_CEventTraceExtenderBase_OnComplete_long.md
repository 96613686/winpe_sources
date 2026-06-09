# Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(long)

- ea: `0x180005ee0`
- end: `0x180005f4a`
- name: `?OnComplete@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJJ@Z`
- size: `106`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ee0`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this,
        unsigned int a2)
{
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx

  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 104LL))(v4);
    v6 = *((_QWORD *)this + 1);
    a2 = v5;
    if ( v6 )
    {
      *((_QWORD *)this + 1) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return a2;
}

```

## disassembly

```asm
0x180005ee0  mov     [rsp+arg_0], rbx
0x180005ee5  push    rdi
0x180005ee6  sub     rsp, 20h
0x180005eea  mov     rbx, rcx
0x180005eed  mov     edi, edx
0x180005eef  mov     rcx, [rcx+8]
0x180005ef3  test    rcx, rcx
0x180005ef6  jz      short loc_180005F22
0x180005ef8  mov     rax, [rcx]
0x180005efb  mov     rax, [rax+68h]
0x180005eff  call    cs:__guard_dispatch_icall_fptr
0x180005f05  mov     rcx, [rbx+8]
0x180005f09  mov     edi, eax
0x180005f0b  test    rcx, rcx
0x180005f0e  jz      short loc_180005F22
0x180005f10  and     qword ptr [rbx+8], 0
0x180005f15  mov     rax, [rcx]
0x180005f18  mov     rax, [rax+10h]
0x180005f1c  call    cs:__guard_dispatch_icall_fptr
0x180005f22  mov     rcx, [rbx+10h]
0x180005f26  test    rcx, rcx
0x180005f29  jz      short loc_180005F3D
0x180005f2b  and     qword ptr [rbx+10h], 0
0x180005f30  mov     rax, [rcx]
0x180005f33  mov     rax, [rax+10h]
0x180005f37  call    cs:__guard_dispatch_icall_fptr
0x180005f3d  mov     eax, edi
0x180005f3f  mov     rbx, [rsp+28h+arg_0]
0x180005f44  add     rsp, 20h
0x180005f48  pop     rdi
0x180005f49  retn
```
