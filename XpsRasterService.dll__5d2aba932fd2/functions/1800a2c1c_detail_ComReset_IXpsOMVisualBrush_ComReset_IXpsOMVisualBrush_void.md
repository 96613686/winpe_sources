# detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)

- ea: `0x1800a2c1c`
- end: `0x1800a2c8a`
- name: `??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `72`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800a4190`
- `0x1800a8e68`
- `0x1800a9ffc`
- `0x1800aa378`
- `0x1800aa594`
- `0x1800aa66c`
- `0x1800aaedc`
- `0x1800ab18c`
- `0x1800ab338`
- `0x1800ac0f4`
- `0x1800ac5a4`
- `0x1800ad308`
- `0x1800ae074`
- `0x1800ae4c8`
- `0x1800af8f4`
- `0x1800aff60`
- `0x1800b0298`
- `0x1800b0710`
- `0x1800b0ff4`
- `0x1800b1150`
- `0x1800b3ecc`
- `0x1800b4a80`
- `0x1800b540c`
- `0x1800b54c4`
- `0x1800b5da8`
- `0x1800b692c`
- `0x1800b8d7c`
- `0x1800b91c0`
- `0x1800b96cc`
- `0x1800b9850`
- `0x1800b9f14`
- `0x1800ba1b4`
- `0x1800bad68`
- `0x1800bb854`
- `0x1800bbabc`
- `0x1800bbca0`
- `0x1800bc69c`
- `0x1800bcbdc`
- `0x1800bd060`
- `0x1800bd288`
- `0x1800bdc84`
- `0x1800be2d4`
- `0x1800be46c`
- `0x1800be6e0`
- `0x1800be794`
- `0x1800bea08`
- `0x1800c0c0b`
- `0x1800c0c1d`
- `0x1800c10f0`
- `0x1800c1126`

## callees

- `0x1800a18b0`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(_QWORD *a1)
{
  __int64 *v1; // rbx
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rdx
  std::_Ref_count_base *v5; // [rsp+28h] [rbp-10h]

  if ( *a1 )
  {
    if ( *(int *)a1[1] >= 0 )
    {
      v1 = (__int64 *)a1[2];
      try
      {
        v2 = (__int64 *)std::shared_ptr<IWICPixelFormatInfo2>::shared_ptr<IWICPixelFormatInfo2>();
        v3 = *v2;
        *v2 = *v1;
        *v1 = v3;
        v4 = v2[1];
        v2[1] = v1[1];
        v1[1] = v4;
        if ( v5 )
          std::_Ref_count_base::_Decref(v5);
      }
      catch ( ... )
      {
        *(_DWORD *)a1[1] = -2147024882;
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    }
  }
}

```

## disassembly

```asm
0x1800a2c1c  mov     [rsp+arg_0], rcx
0x1800a2c21  push    rbx
0x1800a2c22  sub     rsp, 30h
0x1800a2c26  mov     rdx, [rcx]
0x1800a2c29  test    rdx, rdx
0x1800a2c2c  jz      short loc_1800A2C84
0x1800a2c2e  mov     rax, [rcx+8]
0x1800a2c32  cmp     dword ptr [rax], 0
0x1800a2c35  jge     short loc_1800A2C48
0x1800a2c37  mov     rax, [rdx]
0x1800a2c3a  mov     rcx, rdx
0x1800a2c3d  mov     rax, [rax+10h]
0x1800a2c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c46  jmp     short loc_1800A2C84
0x1800a2c48  mov     rbx, [rcx+10h]
0x1800a2c4c  lea     rcx, [rsp+38h+var_18]
0x1800a2c51  call    ??$?0UIWICPixelFormatInfo2@@P6AXPEAUIUnknown@@@Z$0A@@?$shared_ptr@UIWICPixelFormatInfo2@@@std@@QEAA@PEAUIWICPixelFormatInfo2@@P6AXPEAUIUnknown@@@Z@Z; std::shared_ptr<IWICPixelFormatInfo2>::shared_ptr<IWICPixelFormatInfo2>(IWICPixelFormatInfo2 *,void (*)(IUnknown *))
0x1800a2c56  mov     rdx, [rax]
0x1800a2c59  mov     rcx, [rbx]
0x1800a2c5c  mov     [rax], rcx
0x1800a2c5f  mov     [rbx], rdx
0x1800a2c62  mov     rdx, [rax+8]
0x1800a2c66  mov     rcx, [rbx+8]
0x1800a2c6a  mov     [rax+8], rcx
0x1800a2c6e  mov     [rbx+8], rdx
0x1800a2c72  mov     rcx, [rsp+38h+var_10]; this
0x1800a2c77  test    rcx, rcx
0x1800a2c7a  jz      short loc_1800A2C82
0x1800a2c7c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a2c81  nop
0x1800a2c82  jmp     short $+2
0x1800a2c84  add     rsp, 30h
0x1800a2c88  pop     rbx
0x1800a2c89  retn
```
