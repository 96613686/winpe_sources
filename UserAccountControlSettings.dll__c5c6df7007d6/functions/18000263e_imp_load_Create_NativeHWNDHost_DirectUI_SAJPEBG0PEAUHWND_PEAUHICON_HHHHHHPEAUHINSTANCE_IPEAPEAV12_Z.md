# __imp_load_?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z

- ea: `0x18000263e`
- end: `0x18000264a`
- name: `__imp_load_?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z` at `0x18000263e`

## pseudocode

```c
__int64 load__Create_NativeHWNDHost_DirectUI__SAJPEBG0PEAUHWND____PEAUHICON____HHHHHHPEAUHINSTANCE____IPEAPEAV12__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000263e  lea     rax, __imp_?Create@NativeHWNDHost@DirectUI@@SAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@IPEAPEAV12@@Z; DirectUI::NativeHWNDHost::Create(ushort const *,ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,HINSTANCE__ *,uint,DirectUI::NativeHWNDHost * *)
0x180002645  jmp     __tailMerge_dui70_dll
```
