# CSingleSideReducer::BeginGeometry(MGL_WINDING_RULE,unsigned __int64)

- ea: `0x100437810`
- end: `0x100437848`
- name: `?BeginGeometry@CSingleSideReducer@@UEAAJW4MGL_WINDING_RULE@@_K@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100437810`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::BeginGeometry(__int64 a1)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 24LL))(a1 + 48);
  _mm_lfence();
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40), 1);
  return result;
}

```

## disassembly

```asm
0x100437810  push    rbx
0x100437812  sub     rsp, 20h
0x100437816  mov     rax, [rcx+30h]
0x10043781a  mov     rbx, rcx
0x10043781d  add     rcx, 30h ; '0'
0x100437821  call    qword ptr [rax+18h]
0x100437824  lfence
0x100437827  test    eax, eax
0x100437829  js      short loc_100437842
0x10043782b  mov     rcx, [rbx+28h]
0x10043782f  xor     r8d, r8d
0x100437832  mov     rax, [rcx]
0x100437835  lea     edx, [r8+1]
0x100437839  add     rsp, 20h
0x10043783d  pop     rbx
0x10043783e  jmp     qword ptr [rax+18h]
0x100437842  add     rsp, 20h
0x100437846  pop     rbx
0x100437847  retn
```
