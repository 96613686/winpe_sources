# MpPluginFlushLogData

- ea: `0x18003a660`
- end: `0x18003a8fa`
- name: `MpPluginFlushLogData`
- size: `666`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800115a0`
- `0x18003a660`
- `0x18003d758`
- `0x180048df4`
- `0x180080ff8`
- `0x180086770`
- `0x1800d4220`
- `0x1800d42a0`

## string_xrefs

- `0x18003a7b8`: `ConfigurationManager::LogState(), hr = 0x%x`
- `0x18003a6e2`: `PluginConfiguration does not exist.`
- `0x18003a6f3`: `----- PluginConfiguration dump begin -----`
- `0x18003a70b`: `In Memory Path Exclusions (translated and validated):`
- `0x18003a783`: `----- PluginConfiguration dump end -----`

## pseudocode

```c
__int64 __fastcall MpPluginFlushLogData(void (__fastcall *a1)(_WORD *, __int64, _QWORD, __int64))
{
  unsigned int v1; // eax
  __int64 v2; // r8
  __int64 v3; // rbx
  _WORD *v4; // rsi
  __int64 v5; // rdx
  _WORD *v6; // rax
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD v12[2]; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD v13[32]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v14[528]; // [rsp+D8h] [rbp-30h] BYREF

  v1 = sub_180080FF8(*((_QWORD *)lpMem + 1), a1);
  sub_180048DF4(L"FlushPerfLog(), hr = 0x%x", v1);
  v12[0] = 0;
  sub_180086770((char *)lpMem + 120, v12, v2);
  v3 = v12[0];
  if ( v12[0] )
  {
    sub_180048DF4(L"----- PluginConfiguration dump begin -----");
    v4 = *(_WORD **)(*(_QWORD *)(*(_QWORD *)(v3 + 48) + 16LL) + 48LL);
    sub_180048DF4(L"In Memory Path Exclusions (translated and validated):");
    if ( v4 )
    {
      while ( *v4 )
      {
        sub_180048DF4(L"  %ls", v4);
        v5 = 0x3FFFFFFF;
        v6 = v4;
        do
        {
          if ( !*v6 )
            break;
          ++v6;
          --v5;
        }
        while ( v5 );
        v7 = v5 == 0 ? 0x80070057 : 0;
        if ( !v5 )
        {
          if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
            sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 251, &stru_1800F5730, v7);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
          }
          goto LABEL_13;
        }
        v4 += (((2 * (0x3FFFFFFF - v5)) & (unsigned __int64)-(__int64)(v5 != 0)) >> 1) + 1;
        if ( !v4 )
          break;
      }
    }
    sub_180048DF4(L"----- PluginConfiguration dump end -----");
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    }
  }
  else
  {
    sub_180048DF4(L"PluginConfiguration does not exist.");
  }
  v7 = 0;
LABEL_13:
  sub_180048DF4(L"ConfigurationManager::LogState(), hr = 0x%x", v7);
  LODWORD(v12[0]) = 0;
  sub_1800D42A0(v13, 0, 128);
  sub_1800D42A0(v14, 0, 528);
  LOWORD(v13[0]) = 421;
  v13[2] = 43;
  v8 = *((_QWORD *)lpMem + 2) + 40LL;
  v13[1] = 16;
  v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _BYTE *, int, _QWORD *))(*(_QWORD *)v8 + 16LL))(
         v8,
         v13,
         16,
         v14,
         528,
         v12);
  v10 = v9;
  if ( v9 < 0 && off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
    sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 43, &stru_1800ED498, (unsigned int)v9);
  sub_180048DF4(L"RtpFilterManager::LogFilterData(), hr = 0x%x", v10);
  return 0;
}

```

## disassembly

```asm
0x18003a660  mov     rax, rsp
0x18003a663  mov     [rax+10h], rbx
0x18003a667  mov     [rax+18h], rsi
0x18003a66b  mov     [rax+20h], rdi
0x18003a66f  push    rbp
0x18003a670  push    r12
0x18003a672  push    r14
0x18003a674  lea     rbp, [rax-208h]
0x18003a67b  sub     rsp, 2F0h
0x18003a682  mov     rax, cs:__security_cookie
0x18003a689  xor     rax, rsp
0x18003a68c  mov     [rbp+200h+var_20], rax
0x18003a693  mov     rdx, rcx
0x18003a696  mov     rcx, cs:lpMem
0x18003a69d  mov     rcx, [rcx+8]
0x18003a6a1  call    sub_180080FF8
0x18003a6a6  mov     edx, eax
0x18003a6a8  lea     rcx, aFlushperflogHr; "FlushPerfLog(), hr = 0x%x"
0x18003a6af  call    sub_180048DF4
0x18003a6b4  mov     rcx, cs:lpMem
0x18003a6bb  lea     rdx, [rsp+300h+var_2C0]
0x18003a6c0  xor     r14d, r14d
0x18003a6c3  add     rcx, 78h ; 'x'
0x18003a6c7  mov     [rsp+300h+var_2C0], r14
0x18003a6cc  call    sub_180086770
0x18003a6d1  mov     rbx, [rsp+300h+var_2C0]
0x18003a6d6  lea     r12, off_180119DF0
0x18003a6dd  test    rbx, rbx
0x18003a6e0  jnz     short loc_18003A6F3
0x18003a6e2  lea     rcx, aPluginconfigur; "PluginConfiguration does not exist."
0x18003a6e9  call    sub_180048DF4
0x18003a6ee  jmp     loc_18003A7B3
0x18003a6f3  lea     rcx, aPluginconfigur_0; "----- PluginConfiguration dump begin --"...
0x18003a6fa  call    sub_180048DF4
0x18003a6ff  mov     rax, [rbx+30h]
0x18003a703  mov     rcx, [rax+10h]
0x18003a707  mov     rsi, [rcx+30h]
0x18003a70b  lea     rcx, aInMemoryPathEx; "In Memory Path Exclusions (translated a"...
0x18003a712  call    sub_180048DF4
0x18003a717  test    rsi, rsi
0x18003a71a  jz      short loc_18003A783
0x18003a71c  cmp     [rsi], r14w
0x18003a720  jz      short loc_18003A783
0x18003a722  mov     rdx, rsi
0x18003a725  lea     rcx, aLs_0; "  %ls"
0x18003a72c  call    sub_180048DF4
0x18003a731  mov     edx, 3FFFFFFFh
0x18003a736  mov     rax, rsi
0x18003a739  cmp     [rax], r14w
0x18003a73d  jz      short loc_18003A749
0x18003a73f  add     rax, 2
0x18003a743  sub     rdx, 1
0x18003a747  jnz     short loc_18003A739
0x18003a749  mov     rax, rdx
0x18003a74c  neg     rax
0x18003a74f  sbb     edi, edi
0x18003a751  not     edi
0x18003a753  and     edi, 80070057h
0x18003a759  test    rdx, rdx
0x18003a75c  jz      loc_18003A8A3
0x18003a762  mov     ecx, 3FFFFFFFh
0x18003a767  sub     rcx, rdx
0x18003a76a  add     rcx, rcx
0x18003a76d  neg     rdx
0x18003a770  sbb     rax, rax
0x18003a773  and     rax, rcx
0x18003a776  shr     rax, 1
0x18003a779  lea     rsi, [rsi+rax*2]
0x18003a77d  add     rsi, 2
0x18003a781  jnz     short loc_18003A71C
0x18003a783  lea     rcx, aPluginconfigur_1; "----- PluginConfiguration dump end ----"...
0x18003a78a  call    sub_180048DF4
0x18003a78f  or      eax, 0FFFFFFFFh
0x18003a792  lock xadd [rbx+8], eax
0x18003a797  sub     eax, 1
0x18003a79a  jg      short loc_18003A7B3
0x18003a79c  lfence
0x18003a79f  mov     rax, [rbx]
0x18003a7a2  mov     edx, 1
0x18003a7a7  mov     rcx, rbx
0x18003a7aa  mov     rax, [rax]
0x18003a7ad  call    cs:__guard_dispatch_icall_fptr
0x18003a7b3  mov     edi, r14d
0x18003a7b6  mov     edx, edi
0x18003a7b8  lea     rcx, aConfigurationm; "ConfigurationManager::LogState(), hr = "...
0x18003a7bf  call    sub_180048DF4
0x18003a7c4  xor     edx, edx
0x18003a7c6  mov     dword ptr [rsp+300h+var_2C0], r14d
0x18003a7cb  mov     r8d, 80h
0x18003a7d1  lea     rcx, [rsp+300h+var_2B0]
0x18003a7d6  call    sub_1800D42A0
0x18003a7db  mov     ebx, 210h
0x18003a7e0  lea     rcx, [rbp+200h+var_230]
0x18003a7e4  mov     r8d, ebx
0x18003a7e7  xor     edx, edx
0x18003a7e9  call    sub_1800D42A0
0x18003a7ee  mov     rax, cs:lpMem
0x18003a7f5  lea     rdx, [rsp+300h+var_2C0]
0x18003a7fa  mov     [rsp+300h+var_2D8], rdx
0x18003a7ff  lea     r9, [rbp+200h+var_230]
0x18003a803  mov     edi, 2Bh ; '+'
0x18003a808  mov     word ptr [rsp+300h+var_2B0], 1A5h
0x18003a80f  lea     rdx, [rsp+300h+var_2B0]
0x18003a814  mov     [rsp+300h+var_2A8], edi
0x18003a818  mov     rcx, [rax+10h]
0x18003a81c  add     rcx, 28h ; '('
0x18003a820  mov     dword ptr [rsp+300h+var_2E0], ebx
0x18003a824  lea     r8d, [rdi-1Bh]
0x18003a828  mov     [rsp+300h+var_2AC], r8d
0x18003a82d  mov     rax, [rcx]
0x18003a830  mov     rax, [rax+10h]
0x18003a834  call    cs:__guard_dispatch_icall_fptr
0x18003a83a  mov     ebx, eax
0x18003a83c  test    eax, eax
0x18003a83e  jns     short loc_18003A867
0x18003a840  mov     rcx, cs:off_180119DF0
0x18003a847  cmp     rcx, r12
0x18003a84a  jz      short loc_18003A867
0x18003a84c  test    byte ptr [rcx+1Ch], 1
0x18003a850  jz      short loc_18003A867
0x18003a852  mov     rcx, [rcx+10h]
0x18003a856  lea     r8, stru_1800ED498
0x18003a85d  mov     edx, edi
0x18003a85f  mov     r9d, eax
0x18003a862  call    sub_18003D758
0x18003a867  mov     edx, ebx
0x18003a869  lea     rcx, aRtpfiltermanag; "RtpFilterManager::LogFilterData(), hr ="...
0x18003a870  call    sub_180048DF4
0x18003a875  xor     eax, eax
0x18003a877  mov     rcx, [rbp+200h+var_20]
0x18003a87e  xor     rcx, rsp; StackCookie
0x18003a881  call    __security_check_cookie
0x18003a886  lea     r11, [rsp+300h+var_10]
0x18003a88e  mov     rbx, [r11+28h]
0x18003a892  mov     rsi, [r11+30h]
0x18003a896  mov     rdi, [r11+38h]
0x18003a89a  mov     rsp, r11
0x18003a89d  pop     r14
0x18003a89f  pop     r12
0x18003a8a1  pop     rbp
0x18003a8a2  retn
0x18003a8a3  mov     rcx, cs:off_180119DF0
0x18003a8aa  cmp     rcx, r12
0x18003a8ad  jz      short loc_18003A8CD
0x18003a8af  test    byte ptr [rcx+1Ch], 1
0x18003a8b3  jz      short loc_18003A8CD
0x18003a8b5  mov     rcx, [rcx+10h]
0x18003a8b9  lea     r8, stru_1800F5730
0x18003a8c0  mov     edx, 0FBh
0x18003a8c5  mov     r9d, edi
0x18003a8c8  call    sub_18003D758
0x18003a8cd  or      eax, 0FFFFFFFFh
0x18003a8d0  lock xadd [rbx+8], eax
0x18003a8d5  sub     eax, 1
0x18003a8d8  jg      loc_18003A7B6
0x18003a8de  lfence
0x18003a8e1  mov     rax, [rbx]
0x18003a8e4  mov     edx, 1
0x18003a8e9  mov     rcx, rbx
0x18003a8ec  mov     rax, [rax]
0x18003a8ef  call    cs:__guard_dispatch_icall_fptr
0x18003a8f5  jmp     loc_18003A7B6
```
