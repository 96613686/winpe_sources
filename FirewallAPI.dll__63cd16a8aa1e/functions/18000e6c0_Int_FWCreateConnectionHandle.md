# Int_FWCreateConnectionHandle

- ea: `0x18000e6c0`
- end: `0x18000e95a`
- name: `Int_FWCreateConnectionHandle`
- size: `666`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c560`
- `0x18000db60`
- `0x18004f3f0`

## callees

- `0x180005954`
- `0x18000e6c0`
- `0x18000e960`
- `0x18000ebe0`
- `0x1800277b0`
- `0x18003104c`
- `0x180051710`
- `0x180051cc0`
- `0x180051e14`

## import_xrefs

- `fwbase!FwIsMachineLocalHost` at `0x18000e77e`
- `fwbase!FwIsMachineLocalHost` at `0x18000e77e`
- `fwbase!FwHResultToWindowsError` at `0x18000e75d`
- `fwbase!FwHResultToWindowsError` at `0x18000e75d`
- `fwbase!FwStringCopy` at `0x18000e755`
- `fwbase!FwStringCopy` at `0x18000e755`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18000e838`
- `FWPolicyIOMgr!LoadGPExtensionDll` at `0x18000e838`

## pseudocode

```c
__int64 __fastcall Int_FWCreateConnectionHandle(
        __int16 a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6)
{
  FwPolicy2 *v10; // rcx
  unsigned int v11; // eax
  __int64 result; // rax
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // [rsp+20h] [rbp-38h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 349, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v16 = 0;
  if ( !a6 )
  {
    v13 = 87;
    if ( v10 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
      goto LABEL_11;
    v14 = 350;
    v15 = 87;
    goto LABEL_38;
  }
  *(_OWORD *)a6 = 0;
  *(_OWORD *)(a6 + 16) = 0;
  *(_OWORD *)(a6 + 32) = 0;
  *(_OWORD *)(a6 + 48) = 0;
  *(_OWORD *)(a6 + 64) = 0;
  *(_WORD *)a6 = a1;
  *(_DWORD *)(a6 + 72) = a5;
  *(_DWORD *)(a6 + 16) = a3;
  *(_DWORD *)(a6 + 20) = a4;
  v11 = FwStringCopy(a2, a6 + 8);
  LODWORD(result) = FwHResultToWindowsError(v11);
  v13 = result;
  if ( (_DWORD)result )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    v14 = 351;
    goto LABEL_37;
  }
  if ( a3 == 6 )
  {
    LODWORD(result) = LoadGPExtensionDll();
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 352;
    }
    else
    {
      *(_DWORD *)(a6 + 4) = 2;
      LODWORD(result) = Int_FWOpenGPOPolicyStore(a6);
      v13 = result;
      if ( (_DWORD)result )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        v14 = 353;
      }
      else
      {
        result = Int_FWCloseGPOPolicyStore(a6, (a5 >> 3) & 1);
        v13 = result;
        if ( !(_DWORD)result )
          return result;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_11;
        v14 = 354;
      }
    }
LABEL_37:
    v15 = (unsigned int)result;
LABEL_38:
    WPP_SF_d(*((_QWORD *)v10 + 2), v14, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v15);
LABEL_11:
    Int_FWClientHandleCleanup(a6);
    return v13;
  }
  FwIsMachineLocalHost(a2, &v16);
  if ( !a2 || v16 == 1 )
  {
    *(_DWORD *)(a6 + 4) = 0;
    result = Int_FWLocalRpcBindingCreate((RPC_BINDING_HANDLE *)(a6 + 32));
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 355;
      goto LABEL_37;
    }
  }
  else
  {
    *(_DWORD *)(a6 + 4) = 1;
    result = Int_FWRemoteRpcBindingCreate(a2);
    v13 = result;
    if ( (_DWORD)result )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v14 = 356;
      goto LABEL_37;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e6c0  mov     [rsp+arg_0], rbx
0x18000e6c5  mov     [rsp+arg_10], rbp
0x18000e6ca  push    rsi
0x18000e6cb  push    rdi
0x18000e6cc  push    r12
0x18000e6ce  push    r14
0x18000e6d0  push    r15
0x18000e6d2  sub     rsp, 30h
0x18000e6d6  mov     rax, cs:__security_cookie
0x18000e6dd  xor     rax, rsp
0x18000e6e0  mov     [rsp+58h+var_30], rax
0x18000e6e5  mov     rbx, [rsp+58h+arg_28]
0x18000e6ed  mov     edi, r9d
0x18000e6f0  mov     ebp, r8d
0x18000e6f3  mov     rsi, rdx
0x18000e6f6  movzx   r14d, cx
0x18000e6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e701  lea     r12, WPP_GLOBAL_Control
0x18000e708  cmp     rcx, r12
0x18000e70b  jnz     loc_18000E7C8
0x18000e711  xor     r15d, r15d
0x18000e714  mov     [rsp+58h+var_38], r15d
0x18000e719  test    rbx, rbx
0x18000e71c  jz      loc_18000E7F3
0x18000e722  xorps   xmm0, xmm0
0x18000e725  lea     rdx, [rbx+8]
0x18000e729  movups  xmmword ptr [rbx], xmm0
0x18000e72c  mov     rcx, rsi
0x18000e72f  movups  xmmword ptr [rbx+10h], xmm0
0x18000e733  movups  xmmword ptr [rbx+20h], xmm0
0x18000e737  movups  xmmword ptr [rbx+30h], xmm0
0x18000e73b  movups  xmmword ptr [rbx+40h], xmm0
0x18000e73f  mov     [rbx], r14w
0x18000e743  mov     r14d, [rsp+58h+arg_20]
0x18000e74b  mov     [rbx+48h], r14d
0x18000e74f  mov     [rbx+10h], ebp
0x18000e752  mov     [rbx+14h], edi
0x18000e755  call    cs:__imp_FwStringCopy
0x18000e75b  mov     ecx, eax
0x18000e75d  call    cs:__imp_FwHResultToWindowsError
0x18000e763  mov     edi, eax
0x18000e765  test    eax, eax
0x18000e767  jnz     loc_18000E81C
0x18000e76d  cmp     ebp, 6
0x18000e770  jz      loc_18000E838
0x18000e776  lea     rdx, [rsp+58h+var_38]
0x18000e77b  mov     rcx, rsi
0x18000e77e  call    cs:__imp_FwIsMachineLocalHost
0x18000e784  test    rsi, rsi
0x18000e787  jnz     loc_18000E8DA
0x18000e78d  lea     rcx, [rbx+20h]
0x18000e791  mov     [rbx+4], r15d
0x18000e795  call    Int_FWLocalRpcBindingCreate
0x18000e79a  mov     edi, eax
0x18000e79c  test    eax, eax
0x18000e79e  jnz     loc_18000E923
0x18000e7a4  mov     rcx, [rsp+58h+var_30]
0x18000e7a9  xor     rcx, rsp; StackCookie
0x18000e7ac  call    __security_check_cookie
0x18000e7b1  mov     rbx, [rsp+58h+arg_0]
0x18000e7b6  mov     rbp, [rsp+58h+arg_10]
0x18000e7bb  add     rsp, 30h
0x18000e7bf  pop     r15
0x18000e7c1  pop     r14
0x18000e7c3  pop     r12
0x18000e7c5  pop     rdi
0x18000e7c6  pop     rsi
0x18000e7c7  retn
0x18000e7c8  test    byte ptr [rcx+1Ch], 8
0x18000e7cc  jz      loc_18000E711
0x18000e7d2  mov     rcx, [rcx+10h]
0x18000e7d6  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000e7dd  mov     edx, 15Dh
0x18000e7e2  call    WPP_SF_
0x18000e7e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7ee  jmp     loc_18000E711
0x18000e7f3  mov     edi, 57h ; 'W'
0x18000e7f8  cmp     rcx, r12
0x18000e7fb  jnz     short loc_18000E809
0x18000e7fd  mov     rcx, rbx
0x18000e800  call    Int_FWClientHandleCleanup
0x18000e805  mov     eax, edi
0x18000e807  jmp     short loc_18000E7A4
0x18000e809  test    byte ptr [rcx+1Ch], 1
0x18000e80d  jz      short loc_18000E7FD
0x18000e80f  mov     edx, 15Eh
0x18000e814  mov     r9d, edi
0x18000e817  jmp     loc_18000E945
0x18000e81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e823  cmp     rcx, r12
0x18000e826  jz      short loc_18000E7FD
0x18000e828  test    byte ptr [rcx+1Ch], 1
0x18000e82c  jz      short loc_18000E7FD
0x18000e82e  mov     edx, 15Fh
0x18000e833  jmp     loc_18000E942
0x18000e838  call    cs:__imp_LoadGPExtensionDll
0x18000e83e  mov     edi, eax
0x18000e840  test    eax, eax
0x18000e842  jz      short loc_18000E860
0x18000e844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e84b  cmp     rcx, r12
0x18000e84e  jz      short loc_18000E7FD
0x18000e850  test    byte ptr [rcx+1Ch], 1
0x18000e854  jz      short loc_18000E7FD
0x18000e856  mov     edx, 160h
0x18000e85b  jmp     loc_18000E942
0x18000e860  mov     rcx, rbx
0x18000e863  mov     dword ptr [rbx+4], 2
0x18000e86a  call    Int_FWOpenGPOPolicyStore
0x18000e86f  mov     edi, eax
0x18000e871  test    eax, eax
0x18000e873  jz      short loc_18000E899
0x18000e875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e87c  cmp     rcx, r12
0x18000e87f  jz      loc_18000E7FD
0x18000e885  test    byte ptr [rcx+1Ch], 1
0x18000e889  jz      loc_18000E7FD
0x18000e88f  mov     edx, 161h
0x18000e894  jmp     loc_18000E942
0x18000e899  shr     r14d, 3
0x18000e89d  xor     r8d, r8d
0x18000e8a0  and     r14d, 1
0x18000e8a4  mov     rcx, rbx
0x18000e8a7  mov     edx, r14d
0x18000e8aa  call    Int_FWCloseGPOPolicyStore
0x18000e8af  mov     edi, eax
0x18000e8b1  test    eax, eax
0x18000e8b3  jz      loc_18000E7A4
0x18000e8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8c0  cmp     rcx, r12
0x18000e8c3  jz      loc_18000E7FD
0x18000e8c9  test    byte ptr [rcx+1Ch], 1
0x18000e8cd  jz      loc_18000E7FD
0x18000e8d3  mov     edx, 162h
0x18000e8d8  jmp     short loc_18000E942
0x18000e8da  cmp     [rsp+58h+var_38], 1
0x18000e8df  jz      loc_18000E78D
0x18000e8e5  lea     rdx, [rbx+20h]
0x18000e8e9  mov     dword ptr [rbx+4], 1
0x18000e8f0  mov     rcx, rsi; NetworkAddr
0x18000e8f3  call    Int_FWRemoteRpcBindingCreate
0x18000e8f8  mov     edi, eax
0x18000e8fa  test    eax, eax
0x18000e8fc  jz      loc_18000E7A4
0x18000e902  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e909  cmp     rcx, r12
0x18000e90c  jz      loc_18000E7FD
0x18000e912  test    byte ptr [rcx+1Ch], 1
0x18000e916  jz      loc_18000E7FD
0x18000e91c  mov     edx, 164h
0x18000e921  jmp     short loc_18000E942
0x18000e923  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e92a  cmp     rcx, r12
0x18000e92d  jz      loc_18000E7FD
0x18000e933  test    byte ptr [rcx+1Ch], 1
0x18000e937  jz      loc_18000E7FD
0x18000e93d  mov     edx, 163h
0x18000e942  mov     r9d, eax
0x18000e945  mov     rcx, [rcx+10h]
0x18000e949  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000e950  call    WPP_SF_d
0x18000e955  jmp     loc_18000E7FD
```
