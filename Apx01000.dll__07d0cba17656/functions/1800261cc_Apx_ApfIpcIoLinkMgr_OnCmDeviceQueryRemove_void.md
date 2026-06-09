# Apx::ApfIpcIoLinkMgr::OnCmDeviceQueryRemove(void)

- ea: `0x1800261cc`
- end: `0x180026319`
- name: `?OnCmDeviceQueryRemove@ApfIpcIoLinkMgr@Apx@@AEAAKXZ`
- size: `333`
- prototype: `__int64 __fastcall(unsigned __int64 this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180026ef0`

## callees

- `0x18000a12c`
- `0x18001051c`
- `0x1800261cc`
- `0x180027068`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800262db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002623f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002623f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262ce`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800262bf`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800262bf`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLinkMgr::OnCmDeviceQueryRemove(unsigned __int64 this, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  int v5; // eax
  unsigned int v6; // esi
  void *v7; // rcx
  void *v8; // rcx

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
      v4 = (char *)WPP_GLOBAL_Control;
    }
    if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 4u )
      WPP_SF_q(*((_QWORD *)v4 + 2), 48, a3, ~this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v5 = *(_DWORD *)(this + 112);
  if ( v5 )
  {
    v6 = 1223;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids, ~this, v5);
    }
  }
  else
  {
    *(_BYTE *)(this + 117) = 1;
    v6 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(this + 56))(*(_QWORD *)(this + 64), 0, 0);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
    v7 = *(void **)(this + 88);
    if ( v7 )
    {
      CancelIoEx(v7, 0);
      v8 = *(void **)(this + 88);
      if ( v8 )
      {
        CloseHandle(v8);
        *(_QWORD *)(this + 88) = 0;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1800261cc  push    rbx
0x1800261ce  push    rbp
0x1800261cf  push    rsi
0x1800261d0  push    rdi
0x1800261d1  sub     rsp, 38h
0x1800261d5  mov     rbx, rcx
0x1800261d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261df  lea     rbp, WPP_GLOBAL_Control
0x1800261e6  cmp     rcx, rbp
0x1800261e9  jz      short loc_180026238
0x1800261eb  test    byte ptr [rcx+1Ch], 1
0x1800261ef  jz      short loc_180026213
0x1800261f1  cmp     byte ptr [rcx+19h], 5
0x1800261f5  jb      short loc_180026213
0x1800261f7  mov     rcx, [rcx+10h]
0x1800261fb  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026202  mov     edx, 2Fh ; '/'
0x180026207  call    WPP_SF_
0x18002620c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026213  cmp     rcx, rbp
0x180026216  jz      short loc_180026238
0x180026218  test    byte ptr [rcx+1Ch], 80h
0x18002621c  jz      short loc_180026238
0x18002621e  cmp     byte ptr [rcx+19h], 4
0x180026222  jb      short loc_180026238
0x180026224  mov     rcx, [rcx+10h]
0x180026228  mov     r9, rbx
0x18002622b  not     r9
0x18002622e  mov     edx, 30h ; '0'
0x180026233  call    WPP_SF_q
0x180026238  lea     rdi, [rbx+10h]
0x18002623c  mov     rcx, rdi; lpCriticalSection
0x18002623f  call    cs:__imp_EnterCriticalSection
0x180026245  mov     eax, [rbx+70h]
0x180026248  test    eax, eax
0x18002624a  jz      short loc_18002628A
0x18002624c  mov     esi, 4C7h
0x180026251  mov     rcx, cs:WPP_GLOBAL_Control
0x180026258  cmp     rcx, rbp
0x18002625b  jz      short loc_1800262D8
0x18002625d  test    byte ptr [rcx+1Ch], 80h
0x180026261  jz      short loc_1800262D8
0x180026263  cmp     byte ptr [rcx+19h], 4
0x180026267  jb      short loc_1800262D8
0x180026269  mov     rcx, [rcx+10h]
0x18002626d  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026274  not     rbx
0x180026277  mov     [rsp+58h+var_38], eax
0x18002627b  mov     r9, rbx
0x18002627e  mov     edx, 31h ; '1'
0x180026283  call    WPP_SF_qd
0x180026288  jmp     short loc_1800262D8
0x18002628a  mov     rcx, rdi; lpCriticalSection
0x18002628d  mov     byte ptr [rbx+75h], 1
0x180026291  xor     esi, esi
0x180026293  call    cs:__imp_LeaveCriticalSection
0x180026299  mov     rcx, [rbx+40h]
0x18002629d  xor     r8d, r8d
0x1800262a0  mov     rax, [rbx+38h]
0x1800262a4  xor     edx, edx
0x1800262a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262ab  mov     rcx, rdi; lpCriticalSection
0x1800262ae  call    cs:__imp_EnterCriticalSection
0x1800262b4  mov     rcx, [rbx+58h]; hFile
0x1800262b8  test    rcx, rcx
0x1800262bb  jz      short loc_1800262D8
0x1800262bd  xor     edx, edx; lpOverlapped
0x1800262bf  call    cs:__imp_CancelIoEx
0x1800262c5  mov     rcx, [rbx+58h]; hObject
0x1800262c9  test    rcx, rcx
0x1800262cc  jz      short loc_1800262D8
0x1800262ce  call    cs:__imp_CloseHandle
0x1800262d4  mov     [rbx+58h], rsi
0x1800262d8  mov     rcx, rdi; lpCriticalSection
0x1800262db  call    cs:__imp_LeaveCriticalSection
0x1800262e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e8  cmp     rcx, rbp
0x1800262eb  jz      short loc_18002630E
0x1800262ed  test    byte ptr [rcx+1Ch], 1
0x1800262f1  jz      short loc_18002630E
0x1800262f3  cmp     byte ptr [rcx+19h], 5
0x1800262f7  jb      short loc_18002630E
0x1800262f9  mov     rcx, [rcx+10h]
0x1800262fd  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180026304  mov     edx, 32h ; '2'
0x180026309  call    WPP_SF_
0x18002630e  mov     eax, esi
0x180026310  add     rsp, 38h
0x180026314  pop     rdi
0x180026315  pop     rsi
0x180026316  pop     rbp
0x180026317  pop     rbx
0x180026318  retn
```
