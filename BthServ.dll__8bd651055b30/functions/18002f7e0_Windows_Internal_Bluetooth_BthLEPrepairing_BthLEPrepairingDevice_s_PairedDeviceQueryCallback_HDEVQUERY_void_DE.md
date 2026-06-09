# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x18002f7e0`
- end: `0x18002f9d9`
- name: `?s_PairedDeviceQueryCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `505`
- prototype: `void __fastcall(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001790`
- `0x1800114c8`
- `0x180013aa8`
- `0x180013efc`
- `0x18002c308`
- `0x18002f7e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f9a6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f9a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(
        struct HDEVQUERY__ *a1,
        HANDLE *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  _BYTE *v5; // r10
  char v6; // di
  char v7; // dl
  _UNKNOWN **v8; // r9
  __int64 i; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  bool v12; // dl
  _BYTE v13[16]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-58h] BYREF

  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v7 = 0;
        v6 = 1;
      }
      else
      {
        v6 = 1;
        v7 = 1;
      }
      v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
      if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_AND_TRACE_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
        v5 = WPP_GLOBAL_Control;
        v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
      }
      for ( i = 0; (unsigned int)i < *((_DWORD *)a3 + 6); i = (unsigned int)(i + 1) )
      {
        v10 = *((_QWORD *)a3 + 4);
        if ( DEVPKEY_BluetoothLE_PrepairingDeviceId == *(_OWORD *)(v10 + 48 * i)
          && *(_DWORD *)(v10 + 48 * i + 16) == 7
          && *(_DWORD *)(v10 + 48 * i + 32) == 4099
          && *(_DWORD *)(v10 + 48 * i + 36) == 8 )
        {
          if ( **(_QWORD **)(v10 + 48 * i + 40) == *(_QWORD *)((char *)*a2 + 17) )
          {
            if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 4u )
              v6 = 0;
            if ( v6 || v8 != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_sS(
                *((_QWORD *)v5 + 2),
                v6,
                v8 != &WPP_RECORDER_INITIALIZED,
                *((_QWORD *)v5 + 5));
            try
            {
              v11 = std::wstring::wstring(v14, *((_QWORD *)a3 + 2));
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                a2 + 2,
                v13,
                v11);
              std::wstring::~wstring(v14);
            }
            catch ( ... )
            {
              v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
              if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v12,
                  WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                  *((_QWORD *)WPP_GLOBAL_Control + 5));
              return;
            }
          }
          return;
        }
      }
    }
  }
  else if ( *((_DWORD *)a3 + 2) == 1 )
  {
    SetEvent(a2[1]);
  }
}

```

## disassembly

```asm
0x18002f7e0  mov     [rsp+arg_0], rbx
0x18002f7e5  mov     [rsp+arg_18], rsi
0x18002f7ea  push    rdi
0x18002f7eb  push    r12
0x18002f7ed  push    r13
0x18002f7ef  push    r14
0x18002f7f1  push    r15
0x18002f7f3  sub     rsp, 90h
0x18002f7fa  mov     rax, cs:__security_cookie
0x18002f801  xor     rax, rsp
0x18002f804  mov     [rsp+0B8h+var_38], rax
0x18002f80c  mov     rbx, r8
0x18002f80f  mov     rsi, rdx
0x18002f812  mov     ecx, [r8]
0x18002f815  test    ecx, ecx
0x18002f817  jz      loc_18002F99B
0x18002f81d  cmp     ecx, 1
0x18002f820  jnz     loc_18002F9AC
0x18002f826  lea     r12, WPP_GLOBAL_Control
0x18002f82d  mov     r10, cs:WPP_GLOBAL_Control
0x18002f834  cmp     r10, r12
0x18002f837  jz      short loc_18002F847
0x18002f839  cmp     byte ptr [r10+19h], 4
0x18002f83e  jb      short loc_18002F847
0x18002f840  mov     edi, ecx
0x18002f842  mov     dl, dil
0x18002f845  jmp     short loc_18002F84E
0x18002f847  xor     dl, dl
0x18002f849  mov     edi, 1
0x18002f84e  lea     r13, WPP_RECORDER_INITIALIZED
0x18002f855  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002f85c  cmp     r9, r13
0x18002f85f  setnz   r8b
0x18002f863  test    dl, dl
0x18002f865  jnz     short loc_18002F875
0x18002f867  test    r8b, r8b
0x18002f86a  jnz     short loc_18002F875
0x18002f86c  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f873  jmp     short loc_18002F8AC
0x18002f875  mov     rax, [rbx+10h]
0x18002f879  mov     [rsp+0B8h+var_70], rax
0x18002f87e  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f885  mov     [rsp+0B8h+var_80], r14
0x18002f88a  mov     [rsp+0B8h+var_88], 29h ; ')'
0x18002f891  mov     r9, [r10+28h]
0x18002f895  mov     rcx, [r10+10h]
0x18002f899  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002f89e  mov     r10, cs:WPP_GLOBAL_Control
0x18002f8a5  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002f8ac  xor     edx, edx
0x18002f8ae  mov     r8d, cs:dword_18003CF40
0x18002f8b5  mov     r11, qword ptr cs:DEVPKEY_BluetoothLE_PrepairingDeviceId+8
0x18002f8bc  mov     r15, qword ptr cs:DEVPKEY_BluetoothLE_PrepairingDeviceId
0x18002f8c3  cmp     edx, [rbx+18h]
0x18002f8c6  jnb     loc_18002F992
0x18002f8cc  lea     rax, [rdx+rdx*2]
0x18002f8d0  add     rax, rax
0x18002f8d3  mov     rcx, [rbx+20h]
0x18002f8d7  cmp     r15, [rcx+rax*8]
0x18002f8db  jnz     loc_18002F994
0x18002f8e1  cmp     r11, [rcx+rax*8+8]
0x18002f8e6  jnz     loc_18002F994
0x18002f8ec  cmp     r8d, [rcx+rax*8+10h]
0x18002f8f1  jnz     loc_18002F994
0x18002f8f7  cmp     dword ptr [rcx+rax*8+20h], 1003h
0x18002f8ff  jnz     loc_18002F994
0x18002f905  cmp     dword ptr [rcx+rax*8+24h], 8
0x18002f90a  jnz     loc_18002F994
0x18002f910  mov     rdx, [rsi]
0x18002f913  mov     rax, [rcx+rax*8+28h]
0x18002f918  mov     rcx, [rax]
0x18002f91b  cmp     rcx, [rdx+11h]
0x18002f91f  jnz     short loc_18002F992
0x18002f921  cmp     r10, r12
0x18002f924  jz      short loc_18002F92D
0x18002f926  cmp     byte ptr [r10+19h], 4
0x18002f92b  jnb     short loc_18002F930
0x18002f92d  xor     dil, dil
0x18002f930  cmp     r9, r13
0x18002f933  setnz   r8b
0x18002f937  test    dil, dil
0x18002f93a  jnz     short loc_18002F941
0x18002f93c  test    r8b, r8b
0x18002f93f  jz      short loc_18002F966
0x18002f941  mov     rax, [rbx+10h]
0x18002f945  mov     [rsp+0B8h+var_70], rax
0x18002f94a  mov     [rsp+0B8h+var_80], r14
0x18002f94f  mov     [rsp+0B8h+var_88], 2Ah ; '*'
0x18002f956  mov     r9, [r10+28h]
0x18002f95a  mov     dl, dil
0x18002f95d  mov     rcx, [r10+10h]
0x18002f961  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002f966  mov     rdx, [rbx+10h]
0x18002f96a  lea     rcx, [rsp+0B8h+var_58]
0x18002f96f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f974  nop
0x18002f975  mov     r8, rax
0x18002f978  lea     rdx, [rsp+0B8h+var_68]
0x18002f97d  lea     rcx, [rsi+10h]
0x18002f981  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18002f986  nop
0x18002f987  lea     rcx, [rsp+0B8h+var_58]
0x18002f98c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f991  nop
0x18002f992  jmp     short loc_18002F9AC
0x18002f994  add     edx, edi
0x18002f996  jmp     loc_18002F8C3
0x18002f99b  cmp     dword ptr [r8+8], 1
0x18002f9a0  jnz     short loc_18002F9AC
0x18002f9a2  mov     rcx, [rdx+8]; hEvent
0x18002f9a6  call    cs:__imp_SetEvent
0x18002f9ac  mov     rcx, [rsp+0B8h+var_38]
0x18002f9b4  xor     rcx, rsp; StackCookie
0x18002f9b7  call    __security_check_cookie
0x18002f9bc  lea     r11, [rsp+0B8h+var_28]
0x18002f9c4  mov     rbx, [r11+30h]
0x18002f9c8  mov     rsi, [r11+48h]
0x18002f9cc  mov     rsp, r11
0x18002f9cf  pop     r15
0x18002f9d1  pop     r14
0x18002f9d3  pop     r13
0x18002f9d5  pop     r12
0x18002f9d7  pop     rdi
0x18002f9d8  retn
```
