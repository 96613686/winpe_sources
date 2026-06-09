# BdeSvcResumeProtection(ushort const *)

- ea: `0x1800498d0`
- end: `0x180049a4e`
- name: `?BdeSvcResumeProtection@@YAJPEBG@Z`
- size: `382`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004ec40`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x1800498d0`
- `0x1800717fc`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x1800499a7`
- `FVEAPI!FveCommitChanges` at `0x1800499a7`
- `FVEAPI!FveOpenVolumeW` at `0x18004994e`
- `FVEAPI!FveOpenVolumeW` at `0x18004994e`
- `FVEAPI!FveCloseVolume` at `0x1800499f3`
- `FVEAPI!FveCloseVolume` at `0x1800499f3`

## pseudocode

```c
__int64 __fastcall BdeSvcResumeProtection(const unsigned __int16 *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  void *v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = (void *)-1LL;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 398, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_20;
  }
  v4 = FveOpenVolumeW(a1, 1, &v7);
  v3 = v4;
  if ( v4 >= 0 )
  {
    v4 = CFveApiWrapper::DeleteClearKey(v7);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v4 = FveCommitChanges(v7);
      v3 = v4;
      if ( v4 >= 0 )
      {
LABEL_19:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 401;
        goto LABEL_18;
      }
    }
    else
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 400;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 399;
LABEL_18:
      WPP_SF_d(v2[2], v5, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v4);
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v7 != (void *)-1LL )
  {
    FveCloseVolume(v7);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v7 = (void *)-1LL;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 402, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800498d0  mov     [rsp+arg_8], rbx
0x1800498d5  mov     [rsp+arg_10], rsi
0x1800498da  push    rdi
0x1800498db  sub     rsp, 30h
0x1800498df  mov     rax, cs:__security_cookie
0x1800498e6  xor     rax, rsp
0x1800498e9  mov     [rsp+38h+var_10], rax
0x1800498ee  mov     rbx, rcx
0x1800498f1  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x1800498fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180049901  lea     rdi, WPP_GLOBAL_Control
0x180049908  lea     rsi, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004990f  cmp     rcx, rdi
0x180049912  jz      short loc_180049932
0x180049914  test    byte ptr [rcx+1Ch], 20h
0x180049918  jz      short loc_180049932
0x18004991a  mov     rcx, [rcx+10h]
0x18004991e  mov     edx, 18Eh
0x180049923  mov     r8, rsi
0x180049926  call    WPP_SF_
0x18004992b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049932  test    rbx, rbx
0x180049935  jnz     short loc_180049941
0x180049937  mov     ebx, 80070057h
0x18004993c  jmp     loc_1800499E6
0x180049941  lea     r8, [rsp+38h+var_18]
0x180049946  mov     edx, 1
0x18004994b  mov     rcx, rbx
0x18004994e  call    cs:__imp_FveOpenVolumeW
0x180049955  nop     dword ptr [rax+rax+00h]
0x18004995a  mov     ebx, eax
0x18004995c  test    eax, eax
0x18004995e  jns     short loc_180049979
0x180049960  mov     rcx, cs:WPP_GLOBAL_Control
0x180049967  cmp     rcx, rdi
0x18004996a  jz      short loc_1800499E6
0x18004996c  test    byte ptr [rcx+1Ch], 2
0x180049970  jz      short loc_1800499E6
0x180049972  mov     edx, 18Fh
0x180049977  jmp     short loc_1800499D0
0x180049979  mov     rcx, [rsp+38h+var_18]; void *
0x18004997e  call    ?DeleteClearKey@CFveApiWrapper@@SAJPEAX@Z; CFveApiWrapper::DeleteClearKey(void *)
0x180049983  mov     ebx, eax
0x180049985  test    eax, eax
0x180049987  jns     short loc_1800499A2
0x180049989  mov     rcx, cs:WPP_GLOBAL_Control
0x180049990  cmp     rcx, rdi
0x180049993  jz      short loc_1800499E6
0x180049995  test    byte ptr [rcx+1Ch], 2
0x180049999  jz      short loc_1800499E6
0x18004999b  mov     edx, 190h
0x1800499a0  jmp     short loc_1800499D0
0x1800499a2  mov     rcx, [rsp+38h+var_18]
0x1800499a7  call    cs:__imp_FveCommitChanges
0x1800499ae  nop     dword ptr [rax+rax+00h]
0x1800499b3  mov     ebx, eax
0x1800499b5  test    eax, eax
0x1800499b7  jns     short loc_1800499DF
0x1800499b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499c0  cmp     rcx, rdi
0x1800499c3  jz      short loc_1800499E6
0x1800499c5  test    byte ptr [rcx+1Ch], 2
0x1800499c9  jz      short loc_1800499E6
0x1800499cb  mov     edx, 191h
0x1800499d0  mov     rcx, [rcx+10h]
0x1800499d4  mov     r9d, eax
0x1800499d7  mov     r8, rsi
0x1800499da  call    WPP_SF_d
0x1800499df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499e6  cmp     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x1800499ec  jz      short loc_180049A0F
0x1800499ee  mov     rcx, [rsp+38h+var_18]
0x1800499f3  call    cs:__imp_FveCloseVolume
0x1800499fa  nop     dword ptr [rax+rax+00h]
0x1800499ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a06  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFFh
0x180049a0f  cmp     rcx, rdi
0x180049a12  jz      short loc_180049A2E
0x180049a14  test    byte ptr [rcx+1Ch], 20h
0x180049a18  jz      short loc_180049A2E
0x180049a1a  mov     rcx, [rcx+10h]
0x180049a1e  mov     edx, 192h
0x180049a23  mov     r9d, ebx
0x180049a26  mov     r8, rsi
0x180049a29  call    WPP_SF_d
0x180049a2e  mov     eax, ebx
0x180049a30  mov     rcx, [rsp+38h+var_10]
0x180049a35  xor     rcx, rsp; StackCookie
0x180049a38  call    __security_check_cookie
0x180049a3d  mov     rbx, [rsp+38h+arg_8]
0x180049a42  mov     rsi, [rsp+38h+arg_10]
0x180049a47  add     rsp, 30h
0x180049a4b  pop     rdi
0x180049a4c  retn
```
