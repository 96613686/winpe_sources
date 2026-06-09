# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x40acb0`
- end: `0x40ad37`
- name: `?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z`
- size: `135`
- prototype: `void __thiscall __noreturn(_DWORD *ecx0, wil::details *this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x40bc9a`
- `0x40c09d`
- `0x40c146`

## callees

- `0x40a781`
- `0x40acb0`
- `0x40d1d0`
- `0x40eb27`

## pseudocode

```c
void __thiscall __noreturn wil::details::WilFailFast(
        _DWORD *ecx0,
        wil::details *this,
        const struct wil::FailureInfo *a3)
{
  unsigned int v4; // ecx
  unsigned int v5; // eax
  struct _EXCEPTION_RECORD *v6; // [esp+0h] [ebp-58h]
  struct _CONTEXT *v7; // [esp+4h] [ebp-54h]
  unsigned int v8[20]; // [esp+8h] [ebp-50h] BYREF

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(wil::g_pfnWilFailFast, ecx0);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(wil::details::g_pfnFailfastWithContextCallback, ecx0);
  memset(v8, 0, sizeof(v8));
  v4 = ecx0[20];
  v8[0] = -1073740791;
  v8[4] = 1;
  v8[1] = 1;
  v8[5] = 7;
  if ( !v4 )
    wil::details::WilRaiseFailFastException((wil::details *)1, v6, v7, v8[0]);
  v8[6] = ecx0[2];
  v5 = ecx0[10];
  v8[4] = 3;
  v8[7] = v5;
  v8[3] = v4;
  wil::details::WilRaiseFailFastException(0, v6, v7, v8[0]);
}

```

## disassembly

```asm
0x40acb0  mov     edi, edi
0x40acb2  push    ebp
0x40acb3  mov     ebp, esp
0x40acb5  sub     esp, 50h
0x40acb8  push    esi; struct _CONTEXT *
0x40acb9  push    edi; struct _EXCEPTION_RECORD *
0x40acba  mov     edi, ?g_pfnWilFailFast@wil@@3P6G_NABUFailureInfo@1@@_EA
0x40acc0  mov     esi, ecx
0x40acc2  test    edi, edi
0x40acc4  jz      short loc_40ACD1
0x40acc6  push    esi
0x40acc7  mov     ecx, edi
0x40acc9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40accf  call    edi ; ?g_pfnWilFailFast@wil@@3P6G_NABUFailureInfo@1@@_EA
0x40acd1  mov     edi, ?g_pfnFailfastWithContextCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40acd7  test    edi, edi
0x40acd9  jz      short loc_40ACE6
0x40acdb  push    esi
0x40acdc  mov     ecx, edi
0x40acde  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ace4  call    edi ; ?g_pfnFailfastWithContextCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40ace6  push    50h ; 'P'; Size
0x40ace8  lea     eax, [ebp+var_50]
0x40aceb  push    0; Val
0x40aced  push    eax; void *
0x40acee  call    _memset
0x40acf3  mov     ecx, [esi+50h]
0x40acf6  xor     eax, eax
0x40acf8  inc     eax
0x40acf9  mov     [ebp+var_50], 0C0000409h
0x40ad00  add     esp, 0Ch
0x40ad03  mov     [ebp+var_40], eax
0x40ad06  mov     [ebp+var_4C], eax
0x40ad09  mov     [ebp+var_3C], 7
0x40ad10  test    ecx, ecx
0x40ad12  jnz     short loc_40AD1D
0x40ad14  push    eax; this
0x40ad15  lea     ecx, [ebp+var_50]
0x40ad18  call    ?WilRaiseFailFastException@details@wil@@YGXPAU_EXCEPTION_RECORD@@PAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x40ad1d  mov     eax, [esi+8]
0x40ad20  mov     [ebp+var_38], eax
0x40ad23  mov     eax, [esi+28h]
0x40ad26  mov     [ebp+var_40], 3
0x40ad2d  mov     [ebp+var_34], eax
0x40ad30  mov     [ebp+var_44], ecx
0x40ad33  push    0
0x40ad35  jmp     short loc_40AD15
```
