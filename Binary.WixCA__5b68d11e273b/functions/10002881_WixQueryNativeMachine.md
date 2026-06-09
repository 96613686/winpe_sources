# WixQueryNativeMachine

- ea: `0x10002881`
- end: `0x100028f4`
- name: `WixQueryNativeMachine`
- size: `115`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x10002881`
- `0x1000b175`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000f00c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x100028b2`
- `KERNEL32!GetCurrentProcess` at `0x100028b2`

## pseudocode

```c
int __stdcall WixQueryNativeMachine(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  HANDLE CurrentProcess; // eax
  int v4; // eax
  int v6; // [esp+8h] [ebp-4h] BYREF

  v1 = 0;
  v6 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQueryNativeMachine");
  if ( v2 >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    v4 = sub_1000B175(CurrentProcess, &v6);
    v2 = v4;
    if ( v4 >= 0 )
    {
      if ( v4 != 1 )
        sub_1000F00C(L"WIX_NATIVE_MACHINE", (unsigned __int16)v6);
    }
    else
    {
      sub_1000DA66(v4, "Failed to get native machine value.");
    }
  }
  else
  {
    sub_1000DA66(v2, "WixQueryNativeMachine failed to initialize");
  }
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10002881  push    ebp
0x10002882  mov     ebp, esp
0x10002884  push    ecx
0x10002885  push    esi
0x10002886  push    edi
0x10002887  push    offset aWixquerynative_0; "WixQueryNativeMachine"
0x1000288c  push    [ebp+hInstall]; hInstall
0x1000288f  xor     edi, edi
0x10002891  mov     [ebp+var_4], edi
0x10002894  call    sub_1000D51F
0x10002899  mov     esi, eax
0x1000289b  test    esi, esi
0x1000289d  jns     short loc_100028AE
0x1000289f  push    offset aWixquerynative_1; "WixQueryNativeMachine failed to initial"...
0x100028a4  push    esi
0x100028a5  call    sub_1000DA66
0x100028aa  pop     ecx
0x100028ab  pop     ecx
0x100028ac  jmp     short loc_100028DF
0x100028ae  lea     eax, [ebp+var_4]
0x100028b1  push    eax
0x100028b2  call    ds:GetCurrentProcess
0x100028b8  push    eax
0x100028b9  call    sub_1000B175
0x100028be  mov     esi, eax
0x100028c0  test    esi, esi
0x100028c2  jns     short loc_100028CB
0x100028c4  push    offset aFailedToGetNat; "Failed to get native machine value."
0x100028c9  jmp     short loc_100028A4
0x100028cb  cmp     esi, 1
0x100028ce  jz      short loc_100028DF
0x100028d0  movzx   eax, word ptr [ebp+var_4]
0x100028d4  push    eax; int
0x100028d5  push    offset aWixNativeMachi; "WIX_NATIVE_MACHINE"
0x100028da  call    sub_1000F00C
0x100028df  test    esi, esi
0x100028e1  jns     short loc_100028E8
0x100028e3  mov     edi, 643h
0x100028e8  push    edi
0x100028e9  call    sub_1000D4AE
0x100028ee  pop     edi
0x100028ef  pop     esi
0x100028f0  leave
0x100028f1  retn    4
```
