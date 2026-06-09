# CUACSettingsPage::LinkNotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)

- ea: `0x180007820`
- end: `0x1800078b0`
- name: `?LinkNotifyHandler@CUACSettingsPage@@CAHI_K_JPEA_JPEAX@Z`
- size: `144`
- prototype: `_BOOL8 __fastcall(int, __int64, __int64, __int64 *, IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180007820`
- `0x18000c010`

## import_xrefs

- `ole32!CoAllowSetForegroundWindow` at `0x180007858`
- `ole32!CoAllowSetForegroundWindow` at `0x180007858`

## pseudocode

```c
_BOOL8 __fastcall CUACSettingsPage::LinkNotifyHandler(int a1, __int64 a2, __int64 a3, __int64 *a4, IUnknown **a5)
{
  int v6; // edx

  v6 = -2147467259;
  if ( a3 )
  {
    if ( a1 == 78 && ((*(_DWORD *)(a3 + 16) + 4) & 0xFFFFFFFD) == 0 )
    {
      CoAllowSetForegroundWindow(a5[20], 0);
      v6 = ((__int64 (__fastcall *)(IUnknown *, __int64 *, __int64))a5[20]->lpVtbl[1].AddRef)(
             a5[20],
             qword_18000F008,
             101);
      if ( v6 >= 0 )
        *a4 = 1;
    }
  }
  return v6 >= 0;
}

```

## disassembly

```asm
0x180007820  mov     [rsp+arg_0], rbx
0x180007825  push    rdi
0x180007826  sub     rsp, 40h
0x18000782a  mov     rdi, r9
0x18000782d  mov     edx, 80004005h
0x180007832  test    r8, r8
0x180007835  jz      short loc_18000789E
0x180007837  cmp     ecx, 4Eh ; 'N'
0x18000783a  jnz     short loc_18000789E
0x18000783c  mov     eax, [r8+10h]
0x180007840  add     eax, 4
0x180007843  test    eax, 0FFFFFFFDh
0x180007848  jnz     short loc_18000789E
0x18000784a  mov     rbx, [rsp+48h+arg_20]
0x18000784f  xor     edx, edx; lpvReserved
0x180007851  mov     rcx, [rbx+0A0h]; pUnk
0x180007858  call    cs:__imp_CoAllowSetForegroundWindow
0x18000785e  mov     rcx, [rbx+0A0h]
0x180007865  lea     rdx, qword_18000F008
0x18000786c  xor     r9d, r9d
0x18000786f  mov     [rsp+48h+var_20], 0
0x180007878  mov     [rsp+48h+var_28], 0
0x180007881  mov     rax, [rcx]
0x180007884  lea     r8d, [r9+65h]
0x180007888  mov     rax, [rax+20h]
0x18000788c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007891  mov     edx, eax
0x180007893  test    eax, eax
0x180007895  js      short loc_18000789E
0x180007897  mov     qword ptr [rdi], 1
0x18000789e  mov     rbx, [rsp+48h+arg_0]
0x1800078a3  not     edx
0x1800078a5  shr     edx, 1Fh
0x1800078a8  mov     eax, edx
0x1800078aa  add     rsp, 40h
0x1800078ae  pop     rdi
0x1800078af  retn
```
