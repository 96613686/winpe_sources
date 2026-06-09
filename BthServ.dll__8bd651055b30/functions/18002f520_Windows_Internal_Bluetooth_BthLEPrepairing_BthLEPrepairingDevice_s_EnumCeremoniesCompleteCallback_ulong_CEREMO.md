# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)

- ea: `0x18002f520`
- end: `0x18002f6bb`
- name: `?s_EnumCeremoniesCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXKPEBU_CEREMONY@@PEAXJ@Z`
- size: `411`
- prototype: `static void(unsigned int, const struct _CEREMONY *, void *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18002f520`
- `0x180032c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f6b4`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(
        unsigned int a1,
        const struct _CEREMONY *a2,
        _DWORD *a3,
        int a4)
{
  _DWORD *v6; // rdi
  const struct _CEREMONY *v7; // rbp
  unsigned int v8; // eax
  bool v9; // dl
  void *v10; // rcx
  int v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+28h] [rbp-50h]

  v6 = a3;
  v7 = a2;
  if ( a4 >= 0 )
  {
    if ( a1 )
    {
      LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v11,
          v12,
          91,
          (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
      }
      v8 = 10;
      v6[38] = 0;
      if ( a1 < 0xA )
        v8 = a1;
      v6[39] = v8;
      memcpy_0(v6 + 40, v7, 20LL * v8);
      goto LABEL_28;
    }
    goto LABEL_14;
  }
  if ( !a1 )
  {
LABEL_14:
    v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    goto LABEL_28;
  }
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v11,
      v12,
      93,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
  }
LABEL_28:
  v10 = (void *)*((_QWORD *)v6 + 256);
  v6[38] = a4;
  SetEvent(v10);
}

```

## disassembly

```asm
0x18002f520  push    rbx
0x18002f522  push    rbp
0x18002f523  push    rsi
0x18002f524  push    rdi
0x18002f525  sub     rsp, 58h
0x18002f529  mov     ebx, ecx
0x18002f52b  mov     esi, r9d
0x18002f52e  mov     rdi, r8
0x18002f531  mov     rbp, rdx
0x18002f534  test    r9d, r9d
0x18002f537  js      loc_18002F5DD
0x18002f53d  test    ecx, ecx
0x18002f53f  jz      loc_18002F5E1
0x18002f545  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f54c  lea     rax, WPP_GLOBAL_Control
0x18002f553  cmp     rcx, rax
0x18002f556  jz      short loc_18002F562
0x18002f558  cmp     byte ptr [rcx+19h], 4
0x18002f55c  jb      short loc_18002F562
0x18002f55e  mov     dl, 1
0x18002f560  jmp     short loc_18002F564
0x18002f562  xor     dl, dl
0x18002f564  lea     rax, WPP_RECORDER_INITIALIZED
0x18002f56b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002f572  setnz   r8b
0x18002f576  test    dl, dl
0x18002f578  jnz     short loc_18002F57F
0x18002f57a  test    r8b, r8b
0x18002f57d  jz      short loc_18002F5A3
0x18002f57f  mov     r9, [rcx+28h]
0x18002f583  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f58a  mov     rcx, [rcx+10h]
0x18002f58e  mov     [rsp+78h+var_30], ebx
0x18002f592  mov     [rsp+78h+var_40], rax
0x18002f597  mov     [rsp+78h+var_48], 5Bh ; '['
0x18002f59e  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002f5a3  mov     eax, 0Ah
0x18002f5a8  mov     dword ptr [rdi+98h], 0
0x18002f5b2  cmp     ebx, eax
0x18002f5b4  jnb     short loc_18002F5B9
0x18002f5b6  mov     rax, rbx
0x18002f5b9  mov     eax, eax
0x18002f5bb  lea     rcx, [rdi+0A0h]; void *
0x18002f5c2  mov     rdx, rbp; Src
0x18002f5c5  mov     [rdi+9Ch], eax
0x18002f5cb  lea     r8, [rax+rax*4]
0x18002f5cf  shl     r8, 2; Size
0x18002f5d3  call    memcpy_0
0x18002f5d8  jmp     loc_18002F69F
0x18002f5dd  test    ecx, ecx
0x18002f5df  jnz     short loc_18002F641
0x18002f5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5e8  lea     rax, WPP_GLOBAL_Control
0x18002f5ef  cmp     rcx, rax
0x18002f5f2  jz      short loc_18002F5FE
0x18002f5f4  cmp     byte ptr [rcx+19h], 2
0x18002f5f8  jb      short loc_18002F5FE
0x18002f5fa  mov     dl, 1
0x18002f5fc  jmp     short loc_18002F600
0x18002f5fe  xor     dl, dl
0x18002f600  lea     rax, WPP_RECORDER_INITIALIZED
0x18002f607  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002f60e  setnz   r8b
0x18002f612  test    dl, dl
0x18002f614  jnz     short loc_18002F61F
0x18002f616  test    r8b, r8b
0x18002f619  jz      loc_18002F69F
0x18002f61f  mov     r9, [rcx+28h]
0x18002f623  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f62a  mov     rcx, [rcx+10h]
0x18002f62e  mov     [rsp+78h+var_40], rax
0x18002f633  mov     [rsp+78h+var_48], 5Ch ; '\'
0x18002f63a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002f63f  jmp     short loc_18002F69F
0x18002f641  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f648  lea     rax, WPP_GLOBAL_Control
0x18002f64f  cmp     rcx, rax
0x18002f652  jz      short loc_18002F65E
0x18002f654  cmp     byte ptr [rcx+19h], 2
0x18002f658  jb      short loc_18002F65E
0x18002f65a  mov     dl, 1
0x18002f65c  jmp     short loc_18002F660
0x18002f65e  xor     dl, dl
0x18002f660  lea     rax, WPP_RECORDER_INITIALIZED
0x18002f667  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002f66e  setnz   r8b
0x18002f672  test    dl, dl
0x18002f674  jnz     short loc_18002F67B
0x18002f676  test    r8b, r8b
0x18002f679  jz      short loc_18002F69F
0x18002f67b  mov     r9, [rcx+28h]
0x18002f67f  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f686  mov     rcx, [rcx+10h]
0x18002f68a  mov     [rsp+78h+var_30], esi
0x18002f68e  mov     [rsp+78h+var_40], rax
0x18002f693  mov     [rsp+78h+var_48], 5Dh ; ']'
0x18002f69a  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002f69f  mov     rcx, [rdi+800h]
0x18002f6a6  mov     [rdi+98h], esi
0x18002f6ac  add     rsp, 58h
0x18002f6b0  pop     rdi
0x18002f6b1  pop     rsi
0x18002f6b2  pop     rbp
0x18002f6b3  pop     rbx
0x18002f6b4  jmp     cs:__imp_SetEvent
```
