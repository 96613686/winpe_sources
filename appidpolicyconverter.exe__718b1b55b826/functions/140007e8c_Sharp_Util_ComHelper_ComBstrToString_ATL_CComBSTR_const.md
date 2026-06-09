# Sharp::Util::ComHelper::ComBstrToString(ATL::CComBSTR const &)

- ea: `0x140007e8c`
- end: `0x140007ed5`
- name: `?ComBstrToString@ComHelper@Util@Sharp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComBSTR@ATL@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007edc`
- `0x140012a74`
- `0x1400130ec`

## callees

- `0x140007e8c`
- `0x140008498`

## pseudocode

```c
__int64 __fastcall Sharp::Util::ComHelper::ComBstrToString(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdx

  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  v3 = *a2;
  if ( v3 )
    std::wstring::assign(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x140007e8c  mov     [rsp+arg_0], rcx
0x140007e91  push    rbx
0x140007e92  sub     rsp, 30h
0x140007e96  mov     rbx, rcx
0x140007e99  mov     [rsp+38h+var_18], 0
0x140007ea1  mov     qword ptr [rcx+18h], 7
0x140007ea9  mov     qword ptr [rcx+10h], 0
0x140007eb1  xor     eax, eax
0x140007eb3  mov     [rcx], ax
0x140007eb6  mov     [rsp+38h+var_18], 1
0x140007ebe  mov     rdx, [rdx]
0x140007ec1  test    rdx, rdx
0x140007ec4  jz      short loc_140007ECB
0x140007ec6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140007ecb  mov     rax, rbx
0x140007ece  add     rsp, 30h
0x140007ed2  pop     rbx
0x140007ed3  retn
```
