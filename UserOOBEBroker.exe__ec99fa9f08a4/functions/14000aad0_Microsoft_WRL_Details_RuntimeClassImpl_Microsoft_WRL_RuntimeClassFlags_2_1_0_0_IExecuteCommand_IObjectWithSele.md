# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000aad0`
- end: `0x14000ab7d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400071ac`
- `0x140007264`
- `0x14000ab90`

## callees

- `0x14000aad0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IObjectWithSelection>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 2140243376 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data2
        || a2[2] != *(_DWORD *)GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4
        || a2[3] != *(_DWORD *)&GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
    }
    else
    {
      if ( *a2 != 480040379
        || a2[1] != *(_DWORD *)&GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data2
        || a2[2] != *(_DWORD *)GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4
        || a2[3] != *(_DWORD *)&GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
      a1 += 8;
    }
    *a3 = a1;
    goto LABEL_6;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    return (unsigned int)-2147467262;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x14000aad0  push    rbx
0x14000aad2  sub     rsp, 20h
0x14000aad6  xor     ebx, ebx
0x14000aad8  mov     [r8], rbx
0x14000aadb  cmp     [rdx], ebx
0x14000aadd  jnz     short loc_14000AB11
0x14000aadf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000aae5  cmp     [rdx+4], eax
0x14000aae8  jnz     short loc_14000AB3A
0x14000aaea  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000aaf0  cmp     [rdx+8], eax
0x14000aaf3  jnz     short loc_14000AB3A
0x14000aaf5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000aafb  cmp     [rdx+0Ch], eax
0x14000aafe  jnz     short loc_14000AB3A
0x14000ab00  mov     [r8], rcx
0x14000ab03  mov     rax, [rcx]
0x14000ab06  mov     rax, [rax+8]
0x14000ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab0f  jmp     short loc_14000AB3F
0x14000ab11  cmp     dword ptr [rdx], 7F9185B0h
0x14000ab17  jnz     short loc_14000AB47
0x14000ab19  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data2
0x14000ab1f  cmp     [rdx+4], eax
0x14000ab22  jnz     short loc_14000AB3A
0x14000ab24  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4
0x14000ab2a  cmp     [rdx+8], eax
0x14000ab2d  jnz     short loc_14000AB3A
0x14000ab2f  mov     eax, dword ptr cs:_GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54.Data4+4
0x14000ab35  cmp     [rdx+0Ch], eax
0x14000ab38  jz      short loc_14000AB74
0x14000ab3a  mov     ebx, 80004002h
0x14000ab3f  mov     eax, ebx
0x14000ab41  add     rsp, 20h
0x14000ab45  pop     rbx
0x14000ab46  retn
0x14000ab47  cmp     dword ptr [rdx], 1C9CD5BBh
0x14000ab4d  jnz     short loc_14000AB3A
0x14000ab4f  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data2
0x14000ab55  cmp     [rdx+4], eax
0x14000ab58  jnz     short loc_14000AB3A
0x14000ab5a  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4
0x14000ab60  cmp     [rdx+8], eax
0x14000ab63  jnz     short loc_14000AB3A
0x14000ab65  mov     eax, dword ptr cs:_GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c.Data4+4
0x14000ab6b  cmp     [rdx+0Ch], eax
0x14000ab6e  jnz     short loc_14000AB3A
0x14000ab70  add     rcx, 8
0x14000ab74  mov     rax, rcx
0x14000ab77  mov     [r8], rcx
0x14000ab7a  jmp     short loc_14000AB03
```
