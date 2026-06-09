# CRemoveDeviceContextHandler::GetState(IShellItemArray *,int,ulong *)

- ea: `0x180007f80`
- end: `0x1800080f9`
- name: `?GetState@CRemoveDeviceContextHandler@@UEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `377`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *this, struct IShellItemArray *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007f80`
- `0x18000bdec`
- `0x18000be1c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080e3`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetState(
        CRemoveDeviceContextHandler *this,
        struct IShellItemArray *a2,
        __int64 a3,
        unsigned int *a4)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v7; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  PROPVARIANT pvar; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+68h] [rbp+28h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
  *a4 = 2;
  v13 = 0;
  v12 = 0;
  lpVtbl = a2->lpVtbl;
  memset(&pvar, 0, sizeof(pvar));
  v7 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 *))lpVtbl->GetItemAt)(a2, 0, &v12);
  if ( v7 >= 0 )
  {
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
           v12,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           &v13);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v13 + 104LL))(
             v13,
             &PKEY_Devices_LocalMachine,
             &pvar);
      if ( v7 >= 0 )
      {
        if ( pvar.vt == 11 && pvar.iVal == -1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13);
          *a4 = 2;
        }
        else
        {
          *a4 = 0;
        }
      }
    }
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v8, *a4);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
      WPP_SF_d(v9[2], 15, v8, (unsigned int)v7);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  PropVariantClear(&pvar);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007f80  mov     [rsp-18h+arg_0], rbx
0x180007f85  push    rbp
0x180007f86  push    rdi
0x180007f87  push    r14
0x180007f89  mov     rbp, rsp
0x180007f8c  sub     rsp, 40h
0x180007f90  mov     rdi, r9
0x180007f93  mov     rbx, rdx
0x180007f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f9d  lea     r14, WPP_GLOBAL_Control
0x180007fa4  cmp     rcx, r14
0x180007fa7  jz      short loc_180007FBD
0x180007fa9  test    byte ptr [rcx+1Ch], 20h
0x180007fad  jz      short loc_180007FBD
0x180007faf  mov     rcx, [rcx+10h]
0x180007fb3  mov     edx, 0Ch
0x180007fb8  call    WPP_SF_
0x180007fbd  xor     eax, eax
0x180007fbf  mov     dword ptr [rdi], 2
0x180007fc5  mov     qword ptr [rbp+pvar+10h], rax
0x180007fc9  lea     r8, [rbp+arg_8]
0x180007fcd  mov     [rbp+arg_18], rax
0x180007fd1  xorps   xmm0, xmm0
0x180007fd4  mov     [rbp+arg_8], rax
0x180007fd8  xor     edx, edx
0x180007fda  mov     rax, [rbx]
0x180007fdd  mov     rcx, rbx
0x180007fe0  movups  xmmword ptr [rbp+pvar], xmm0
0x180007fe4  mov     rax, [rax+40h]
0x180007fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fed  mov     ebx, eax
0x180007fef  test    eax, eax
0x180007ff1  js      loc_180008084
0x180007ff7  mov     rcx, [rbp+arg_8]
0x180007ffb  lea     r8, [rbp+arg_18]
0x180007fff  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180008006  mov     rax, [rcx]
0x180008009  mov     rax, [rax]
0x18000800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008011  mov     rcx, [rbp+arg_8]
0x180008015  mov     ebx, eax
0x180008017  mov     rax, [rcx]
0x18000801a  mov     rax, [rax+10h]
0x18000801e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008023  test    ebx, ebx
0x180008025  js      short loc_180008084
0x180008027  mov     rcx, [rbp+arg_18]
0x18000802b  lea     r8, [rbp+pvar]
0x18000802f  lea     rdx, PKEY_Devices_LocalMachine
0x180008036  mov     rax, [rcx]
0x180008039  mov     rax, [rax+68h]
0x18000803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008042  mov     ebx, eax
0x180008044  test    eax, eax
0x180008046  js      short loc_180008084
0x180008048  cmp     word ptr [rbp+pvar], 0Bh
0x18000804d  jnz     short loc_18000807E
0x18000804f  cmp     word ptr [rbp+pvar+8], 0FFFFh
0x180008054  jnz     short loc_18000807E
0x180008056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805d  cmp     rcx, r14
0x180008060  jz      short loc_180008076
0x180008062  test    byte ptr [rcx+1Ch], 8
0x180008066  jz      short loc_180008076
0x180008068  mov     rcx, [rcx+10h]
0x18000806c  mov     edx, 0Dh
0x180008071  call    WPP_SF_
0x180008076  mov     dword ptr [rdi], 2
0x18000807c  jmp     short loc_180008084
0x18000807e  mov     dword ptr [rdi], 0
0x180008084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000808b  cmp     rcx, r14
0x18000808e  jz      short loc_1800080CA
0x180008090  test    byte ptr [rcx+1Ch], 8
0x180008094  jz      short loc_1800080AE
0x180008096  mov     r9d, [rdi]
0x180008099  mov     edx, 0Eh
0x18000809e  mov     rcx, [rcx+10h]
0x1800080a2  call    WPP_SF_d
0x1800080a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ae  cmp     rcx, r14
0x1800080b1  jz      short loc_1800080CA
0x1800080b3  test    byte ptr [rcx+1Ch], 20h
0x1800080b7  jz      short loc_1800080CA
0x1800080b9  mov     rcx, [rcx+10h]
0x1800080bd  mov     edx, 0Fh
0x1800080c2  mov     r9d, ebx
0x1800080c5  call    WPP_SF_d
0x1800080ca  mov     rcx, [rbp+arg_18]
0x1800080ce  test    rcx, rcx
0x1800080d1  jz      short loc_1800080DF
0x1800080d3  mov     rax, [rcx]
0x1800080d6  mov     rax, [rax+10h]
0x1800080da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080df  lea     rcx, [rbp+pvar]; pvar
0x1800080e3  call    cs:__imp_PropVariantClear
0x1800080e9  mov     eax, ebx
0x1800080eb  mov     rbx, [rsp+40h+arg_0]
0x1800080f0  add     rsp, 40h
0x1800080f4  pop     r14
0x1800080f6  pop     rdi
0x1800080f7  pop     rbp
0x1800080f8  retn
```
