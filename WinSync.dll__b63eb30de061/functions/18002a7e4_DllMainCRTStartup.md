# __DllMainCRTStartup

- ea: `0x18002a7e4`
- end: `0x18002a9f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002a7a0`

## callees

- `0x180023910`
- `0x18002a570`
- `0x18002a7e4`
- `0x18002a9f6`
- `0x1800932b0`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800AA0E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800AA0E4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800AA0E4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x18002a7e4  mov     [rsp+lpvReserved], r8
0x18002a7e9  mov     [rsp+arg_8], edx
0x18002a7ed  mov     [rsp+arg_0], rcx
0x18002a7f2  push    rbx
0x18002a7f3  push    rsi
0x18002a7f4  push    rdi
0x18002a7f5  sub     rsp, 0F0h
0x18002a7fc  mov     edi, edx
0x18002a7fe  mov     rsi, rcx
0x18002a801  mov     ebx, 1
0x18002a806  cmp     edx, ebx
0x18002a808  ja      short loc_18002A810
0x18002a80a  mov     cs:__native_dllmain_reason, edx
0x18002a810  test    edx, edx
0x18002a812  jnz     short loc_18002A827
0x18002a814  cmp     cs:dword_1800AA0E0, edx
0x18002a81a  jnz     short loc_18002A827
0x18002a81c  xor     ebx, ebx
0x18002a81e  mov     [rsp+108h+var_E8], ebx
0x18002a822  jmp     loc_18002A9D4
0x18002a827  lea     eax, [rdx-1]
0x18002a82a  cmp     eax, 1
0x18002a82d  ja      loc_18002A8B4
0x18002a833  mov     rax, cs:_pRawDllMain
0x18002a83a  test    rax, rax
0x18002a83d  jz      short loc_18002A875
0x18002a83f  cmp     edx, 1
0x18002a842  jnz     short loc_18002A84A
0x18002a844  mov     cs:dword_1800AA0E4, edx
0x18002a84a  mov     r8, [rsp+108h+lpvReserved]
0x18002a852  call    cs:__guard_dispatch_icall_fptr
0x18002a858  mov     ebx, eax
0x18002a85a  mov     [rsp+108h+var_E8], eax
0x18002a85e  jmp     short loc_18002A875
0x18002a860  xor     ebx, ebx
0x18002a862  mov     [rsp+108h+var_E8], ebx
0x18002a866  mov     edi, [rsp+108h+arg_8]
0x18002a86d  mov     rsi, [rsp+108h+arg_0]
0x18002a875  test    ebx, ebx
0x18002a877  jz      loc_18002A9D4
0x18002a87d  mov     r8, [rsp+108h+lpvReserved]
0x18002a885  mov     edx, edi
0x18002a887  mov     rcx, rsi
0x18002a88a  call    _CRT_INIT
0x18002a88f  mov     ebx, eax
0x18002a891  mov     [rsp+108h+var_E8], eax
0x18002a895  jmp     short loc_18002A8AC
0x18002a897  xor     ebx, ebx
0x18002a899  mov     [rsp+108h+var_E8], ebx
0x18002a89d  mov     edi, [rsp+108h+arg_8]
0x18002a8a4  mov     rsi, [rsp+108h+arg_0]
0x18002a8ac  test    ebx, ebx
0x18002a8ae  jz      loc_18002A9D4
0x18002a8b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18002a8bc  mov     edx, edi; fdwReason
0x18002a8be  mov     rcx, rsi; hinstDLL
0x18002a8c1  call    DllMain
0x18002a8c6  mov     ebx, eax
0x18002a8c8  mov     [rsp+108h+var_E8], eax
0x18002a8cc  jmp     short loc_18002A8E3
0x18002a8ce  xor     ebx, ebx
0x18002a8d0  mov     [rsp+108h+var_E8], ebx
0x18002a8d4  mov     edi, [rsp+108h+arg_8]
0x18002a8db  mov     rsi, [rsp+108h+arg_0]
0x18002a8e3  cmp     edi, 1
0x18002a8e6  jnz     short loc_18002A95F
0x18002a8e8  test    ebx, ebx
0x18002a8ea  jnz     short loc_18002A95F
0x18002a8ec  xor     r8d, r8d; lpvReserved
0x18002a8ef  xor     edx, edx; fdwReason
0x18002a8f1  mov     rcx, rsi; hinstDLL
0x18002a8f4  call    DllMain
0x18002a8f9  jmp     short loc_18002A90E
0x18002a8fb  mov     edi, [rsp+108h+arg_8]
0x18002a902  mov     rsi, [rsp+108h+arg_0]
0x18002a90a  mov     ebx, [rsp+108h+var_E8]
0x18002a90e  xor     r8d, r8d
0x18002a911  xor     edx, edx
0x18002a913  mov     rcx, rsi
0x18002a916  call    _CRT_INIT
0x18002a91b  jmp     short loc_18002A930
0x18002a91d  mov     edi, [rsp+108h+arg_8]
0x18002a924  mov     rsi, [rsp+108h+arg_0]
0x18002a92c  mov     ebx, [rsp+108h+var_E8]
0x18002a930  mov     rax, cs:_pRawDllMain
0x18002a937  test    rax, rax
0x18002a93a  jz      short loc_18002A95F
0x18002a93c  xor     r8d, r8d
0x18002a93f  xor     edx, edx
0x18002a941  mov     rcx, rsi
0x18002a944  call    cs:__guard_dispatch_icall_fptr
0x18002a94a  jmp     short loc_18002A95F
0x18002a94c  mov     edi, [rsp+108h+arg_8]
0x18002a953  mov     rsi, [rsp+108h+arg_0]
0x18002a95b  mov     ebx, [rsp+108h+var_E8]
0x18002a95f  test    edi, edi
0x18002a961  jz      short loc_18002A968
0x18002a963  cmp     edi, 3
0x18002a966  jnz     short loc_18002A9D4
0x18002a968  mov     r8, [rsp+108h+lpvReserved]
0x18002a970  mov     edx, edi
0x18002a972  mov     rcx, rsi
0x18002a975  call    _CRT_INIT
0x18002a97a  mov     ebx, eax
0x18002a97c  mov     [rsp+108h+var_E8], eax
0x18002a980  jmp     short loc_18002A997
0x18002a982  xor     ebx, ebx
0x18002a984  mov     [rsp+108h+var_E8], ebx
0x18002a988  mov     edi, [rsp+108h+arg_8]
0x18002a98f  mov     rsi, [rsp+108h+arg_0]
0x18002a997  mov     rax, cs:_pRawDllMain
0x18002a99e  test    rax, rax
0x18002a9a1  jz      short loc_18002A9D4
0x18002a9a3  cmp     cs:dword_1800AA0E4, 0
0x18002a9aa  jz      short loc_18002A9D4
0x18002a9ac  mov     r8, [rsp+108h+lpvReserved]
0x18002a9b4  mov     edx, edi
0x18002a9b6  mov     rcx, rsi
0x18002a9b9  call    cs:__guard_dispatch_icall_fptr
0x18002a9bf  mov     ebx, eax
0x18002a9c1  mov     [rsp+108h+var_E8], eax
0x18002a9c5  jmp     short loc_18002A9D4
0x18002a9c7  xor     ebx, ebx
0x18002a9c9  mov     [rsp+108h+var_E8], ebx
0x18002a9cd  mov     edi, [rsp+108h+arg_8]
0x18002a9d4  cmp     edi, 1
0x18002a9d7  ja      short loc_18002A9E3
0x18002a9d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18002a9e3  mov     eax, ebx
0x18002a9e5  add     rsp, 0F0h
0x18002a9ec  pop     rdi
0x18002a9ed  pop     rsi
0x18002a9ee  pop     rbx
0x18002a9ef  retn
0x180093320  push    rbp
0x180093322  sub     rsp, 20h
0x180093326  mov     rbp, rdx
0x180093329  mov     rax, [rcx]
0x18009332c  mov     edx, [rax]
0x18009332e  mov     [rbp+0A8h], rcx
0x180093335  mov     [rbp+28h], edx
0x180093338  mov     eax, [rbp+28h]
0x18009333b  cmp     eax, 0E06D7363h
0x180093340  jnz     short loc_180093356
0x180093342  mov     rdx, [rbp+0A8h]
0x180093349  mov     ecx, [rbp+28h]
0x18009334c  call    _XcptFilter_0
0x180093351  mov     [rbp+30h], eax
0x180093354  jmp     short loc_18009335D
0x180093356  mov     dword ptr [rbp+30h], 0
0x18009335d  mov     eax, [rbp+30h]
0x180093360  add     rsp, 20h
0x180093364  pop     rbp
0x180093365  retn
0x180093367  push    rbp
0x180093369  sub     rsp, 20h
0x18009336d  mov     rbp, rdx
0x180093370  mov     rax, [rcx]
0x180093373  mov     edx, [rax]
0x180093375  mov     [rbp+0B0h], rcx
0x18009337c  mov     [rbp+38h], edx
0x18009337f  mov     eax, [rbp+38h]
0x180093382  cmp     eax, 0E06D7363h
0x180093387  jnz     short loc_18009339D
0x180093389  mov     rdx, [rbp+0B0h]
0x180093390  mov     ecx, [rbp+38h]
0x180093393  call    _XcptFilter_0
0x180093398  mov     [rbp+40h], eax
0x18009339b  jmp     short loc_1800933A4
0x18009339d  mov     dword ptr [rbp+40h], 0
0x1800933a4  mov     eax, [rbp+40h]
0x1800933a7  add     rsp, 20h
0x1800933ab  pop     rbp
0x1800933ac  retn
0x1800933ae  push    rbp
0x1800933b0  sub     rsp, 20h
0x1800933b4  mov     rbp, rdx
0x1800933b7  mov     rax, [rcx]
0x1800933ba  mov     edx, [rax]
0x1800933bc  mov     [rbp+0B8h], rcx
0x1800933c3  mov     [rbp+48h], edx
0x1800933c6  mov     eax, [rbp+48h]
0x1800933c9  cmp     eax, 0E06D7363h
0x1800933ce  jnz     short loc_1800933E4
0x1800933d0  mov     rdx, [rbp+0B8h]
0x1800933d7  mov     ecx, [rbp+48h]
0x1800933da  call    _XcptFilter_0
0x1800933df  mov     [rbp+50h], eax
0x1800933e2  jmp     short loc_1800933EB
0x1800933e4  mov     dword ptr [rbp+50h], 0
0x1800933eb  mov     eax, [rbp+50h]
0x1800933ee  add     rsp, 20h
0x1800933f2  pop     rbp
0x1800933f3  retn
0x1800933f5  push    rbp
0x1800933f7  sub     rsp, 20h
0x1800933fb  mov     rbp, rdx
0x1800933fe  mov     rax, [rcx]
0x180093401  mov     edx, [rax]
0x180093403  mov     [rbp+0C0h], rcx
0x18009340a  mov     [rbp+58h], edx
0x18009340d  mov     eax, [rbp+58h]
0x180093410  cmp     eax, 0E06D7363h
0x180093415  jnz     short loc_18009342B
0x180093417  mov     rdx, [rbp+0C0h]
0x18009341e  mov     ecx, [rbp+58h]
0x180093421  call    _XcptFilter_0
0x180093426  mov     [rbp+60h], eax
0x180093429  jmp     short loc_180093432
0x18009342b  mov     dword ptr [rbp+60h], 0
0x180093432  mov     eax, [rbp+60h]
0x180093435  add     rsp, 20h
0x180093439  pop     rbp
0x18009343a  retn
0x18009343c  push    rbp
0x18009343e  sub     rsp, 20h
0x180093442  mov     rbp, rdx
0x180093445  mov     rax, [rcx]
0x180093448  mov     edx, [rax]
0x18009344a  mov     [rbp+0C8h], rcx
0x180093451  mov     [rbp+68h], edx
0x180093454  mov     eax, [rbp+68h]
0x180093457  cmp     eax, 0E06D7363h
0x18009345c  jnz     short loc_180093472
0x18009345e  mov     rdx, [rbp+0C8h]
0x180093465  mov     ecx, [rbp+68h]
0x180093468  call    _XcptFilter_0
0x18009346d  mov     [rbp+70h], eax
0x180093470  jmp     short loc_180093479
0x180093472  mov     dword ptr [rbp+70h], 0
0x180093479  mov     eax, [rbp+70h]
0x18009347c  add     rsp, 20h
0x180093480  pop     rbp
0x180093481  retn
0x180093483  push    rbp
0x180093485  sub     rsp, 20h
0x180093489  mov     rbp, rdx
0x18009348c  mov     rax, [rcx]
0x18009348f  mov     edx, [rax]
0x180093491  mov     [rbp+0D0h], rcx
0x180093498  mov     [rbp+78h], edx
0x18009349b  mov     eax, [rbp+78h]
0x18009349e  cmp     eax, 0E06D7363h
0x1800934a3  jnz     short loc_1800934BC
0x1800934a5  mov     rdx, [rbp+0D0h]
0x1800934ac  mov     ecx, [rbp+78h]
0x1800934af  call    _XcptFilter_0
0x1800934b4  mov     [rbp+80h], eax
0x1800934ba  jmp     short loc_1800934C6
0x1800934bc  mov     dword ptr [rbp+80h], 0
0x1800934c6  mov     eax, [rbp+80h]
0x1800934cc  add     rsp, 20h
0x1800934d0  pop     rbp
0x1800934d1  retn
0x1800934d3  push    rbp
0x1800934d5  sub     rsp, 20h
0x1800934d9  mov     rbp, rdx
0x1800934dc  mov     rax, [rcx]
0x1800934df  mov     edx, [rax]
0x1800934e1  mov     [rbp+0D8h], rcx
0x1800934e8  mov     [rbp+88h], edx
0x1800934ee  mov     eax, [rbp+88h]
0x1800934f4  cmp     eax, 0E06D7363h
0x1800934f9  jnz     short loc_180093515
0x1800934fb  mov     rdx, [rbp+0D8h]
0x180093502  mov     ecx, [rbp+88h]
0x180093508  call    _XcptFilter_0
0x18009350d  mov     [rbp+90h], eax
0x180093513  jmp     short loc_18009351F
0x180093515  mov     dword ptr [rbp+90h], 0
0x18009351f  mov     eax, [rbp+90h]
0x180093525  add     rsp, 20h
0x180093529  pop     rbp
0x18009352a  retn
0x18009352c  push    rbp
0x18009352e  sub     rsp, 20h
0x180093532  mov     rbp, rdx
0x180093535  mov     rax, [rcx]
0x180093538  mov     edx, [rax]
0x18009353a  mov     [rbp+0E0h], rcx
0x180093541  mov     [rbp+98h], edx
0x180093547  mov     eax, [rbp+98h]
0x18009354d  cmp     eax, 0E06D7363h
0x180093552  jnz     short loc_18009356E
0x180093554  mov     rdx, [rbp+0E0h]
0x18009355b  mov     ecx, [rbp+98h]
0x180093561  call    _XcptFilter_0
0x180093566  mov     [rbp+0A0h], eax
0x18009356c  jmp     short loc_180093578
0x18009356e  mov     dword ptr [rbp+0A0h], 0
0x180093578  mov     eax, [rbp+0A0h]
0x18009357e  add     rsp, 20h
0x180093582  pop     rbp
0x180093583  retn
0x180093585  push    rbp
0x180093587  sub     rsp, 20h
0x18009358b  mov     rbp, rdx
0x18009358e  cmp     dword ptr [rbp+118h], 1
0x180093595  ja      short loc_1800935A1
0x180093597  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
