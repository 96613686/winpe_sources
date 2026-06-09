# Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *>::__abi_QueryInterface(Platform::Guid &,void * *)

- ea: `0x1400200d0`
- end: `0x1400201e7`
- name: `?__abi_QueryInterface@?$TypedEventHandler@PE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@2345@@Foundation@Windows@@UE$AAAJAEAVGuid@Platform@@PEAPEAX@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400201f0`
- `0x140020200`

## callees

- `0x140008470`
- `0x1400200d0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::TypedEventHandler<Windows::UI::Xaml::Controls::WebView __gc *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs __gc *>::__abi_QueryInterface(
        _QWORD *a1,
        __int64 a2,
        void **a3)
{
  if ( !*(_DWORD *)a2 )
  {
    if ( *(_DWORD *)(a2 + 4) != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || *(_DWORD *)(a2 + 8) != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_9;
    }
    if ( *(_DWORD *)(a2 + 12) == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == 1091647223
    && *(_DWORD *)(a2 + 4) == 1503426317
    && *(_DWORD *)(a2 + 8) == 91047301
    && *(_DWORD *)(a2 + 12) == -1726518726 )
  {
LABEL_18:
    *a3 = a1;
    if ( a1[3] )
    {
      if ( *(int *)(a1[3] + 12LL) >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(a1[3] + 12LL));
    }
    return 0;
  }
LABEL_9:
  if ( (-(__int64)(a1[4] != 0) & (unsigned __int64)(a1 + 3)) != 0 && *(_DWORD *)a2 == -1796592748 )
  {
    if ( *(_DWORD *)(a2 + 4) != 1239476684 || *(_DWORD *)(a2 + 8) != 1693384640 )
      goto LABEL_21;
    if ( *(_DWORD *)(a2 + 12) == -1873047606 )
      goto LABEL_18;
  }
  if ( *(_DWORD *)a2 == -1646148300
    && *(_DWORD *)(a2 + 4) == 299920097
    && *(_DWORD *)(a2 + 8) == -1457987196
    && *(_DWORD *)(a2 + 12) == 1069923333 )
  {
    goto LABEL_18;
  }
LABEL_21:
  if ( (-(__int64)(a1[4] != 0) & (unsigned __int64)(a1 + 3)) != 0
    && !(unsigned int)__abi_FTMWeakRefData::__abi_QueryInterface(
                        (__abi_FTMWeakRefData *)((unsigned __int64)(a1 + 3) & -(__int64)(a1[4] != 0)),
                        (struct Platform::Guid *)a2,
                        a3) )
  {
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x1400200d0  sub     rsp, 28h
0x1400200d4  cmp     dword ptr [rdx], 0
0x1400200d7  mov     r9, rcx
0x1400200da  jnz     short loc_140020101
0x1400200dc  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1400200e2  cmp     [rdx+4], eax
0x1400200e5  jnz     short loc_14002012A
0x1400200e7  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1400200ed  cmp     [rdx+8], eax
0x1400200f0  jnz     short loc_14002012A
0x1400200f2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1400200f8  cmp     [rdx+0Ch], eax
0x1400200fb  jz      loc_14002018F
0x140020101  cmp     dword ptr [rdx], 411136F7h
0x140020107  jnz     short loc_14002012A
0x140020109  mov     eax, cs:dword_14003B7CC
0x14002010f  cmp     [rdx+4], eax
0x140020112  jnz     short loc_14002012A
0x140020114  mov     eax, cs:dword_14003B7D0
0x14002011a  cmp     [rdx+8], eax
0x14002011d  jnz     short loc_14002012A
0x14002011f  mov     eax, cs:dword_14003B7D4
0x140020125  cmp     [rdx+0Ch], eax
0x140020128  jz      short loc_14002018F
0x14002012a  mov     rax, [rcx+20h]
0x14002012e  lea     r10, [rcx+18h]
0x140020132  neg     rax
0x140020135  sbb     rax, rax
0x140020138  test    r10, rax
0x14002013b  jz      short loc_140020166
0x14002013d  cmp     dword ptr [rdx], 94EA2B94h
0x140020143  jnz     short loc_140020166
0x140020145  mov     eax, cs:dword_140039C6C
0x14002014b  cmp     [rdx+4], eax
0x14002014e  jnz     short loc_1400201B0
0x140020150  mov     eax, cs:dword_140039C70
0x140020156  cmp     [rdx+8], eax
0x140020159  jnz     short loc_1400201B0
0x14002015b  mov     eax, cs:dword_140039C74
0x140020161  cmp     [rdx+0Ch], eax
0x140020164  jz      short loc_14002018F
0x140020166  cmp     dword ptr [rdx], 9DE1C534h
0x14002016c  jnz     short loc_1400201B0
0x14002016e  mov     eax, cs:dword_14003B89C
0x140020174  cmp     [rdx+4], eax
0x140020177  jnz     short loc_1400201B0
0x140020179  mov     eax, cs:dword_14003B8A0
0x14002017f  cmp     [rdx+8], eax
0x140020182  jnz     short loc_1400201B0
0x140020184  mov     eax, cs:dword_14003B8A4
0x14002018a  cmp     [rdx+0Ch], eax
0x14002018d  jnz     short loc_1400201B0
0x14002018f  mov     [r8], r9
0x140020192  mov     rax, [rcx+18h]
0x140020196  test    rax, rax
0x140020199  jz      short loc_1400201D9
0x14002019b  mov     rax, [rcx+18h]
0x14002019f  mov     ecx, [rax+0Ch]
0x1400201a2  test    ecx, ecx
0x1400201a4  js      short loc_1400201D9
0x1400201a6  mov     rax, [r9+18h]
0x1400201aa  lock inc dword ptr [rax+0Ch]
0x1400201ae  jmp     short loc_1400201D9
0x1400201b0  mov     rax, [rcx+20h]
0x1400201b4  add     rcx, 18h
0x1400201b8  neg     rax
0x1400201bb  sbb     rax, rax
0x1400201be  test    rcx, rax
0x1400201c1  jz      short loc_1400201DD
0x1400201c3  mov     rax, [r9+20h]
0x1400201c7  neg     rax
0x1400201ca  sbb     rcx, rcx
0x1400201cd  and     rcx, r10; this
0x1400201d0  call    ?__abi_QueryInterface@__abi_FTMWeakRefData@@QEAAJAEAVGuid@Platform@@PEAPEAX@Z; __abi_FTMWeakRefData::__abi_QueryInterface(Platform::Guid &,void * *)
0x1400201d5  test    eax, eax
0x1400201d7  jnz     short loc_1400201DD
0x1400201d9  xor     eax, eax
0x1400201db  jmp     short loc_1400201E2
0x1400201dd  mov     eax, 80004002h
0x1400201e2  add     rsp, 28h
0x1400201e6  retn
```
