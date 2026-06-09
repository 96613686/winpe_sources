# ChangeApplicationServices::SetDestinationKnowledge(ISyncKnowledge *,IForgottenKnowledge *)

- ea: `0x18004a7f0`
- end: `0x18004a8f4`
- name: `?SetDestinationKnowledge@ChangeApplicationServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@@Z`
- size: `260`
- prototype: `int(ChangeApplicationServices *__hidden this, struct ISyncKnowledge *, struct IForgottenKnowledge *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180047300`
- `0x18004a7f0`
- `0x18004a8fc`

## string_xrefs

- `0x18004a829`: `ChangeApplicationServices::SetDestinationKnowledge`
- `0x18004a8c9`: `ChangeApplicationServices::SetDestinationKnowledge`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::SetDestinationKnowledge(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge *a3)
{
  ChangeApplicationServices *v6; // rcx
  int v7; // ebx
  ChangeApplicationServices *v8; // rcx

  v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::SetDestinationKnowledge");
    v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_8;
  if ( *((_DWORD *)this + 9) == 3 )
  {
    if ( !a3 )
    {
LABEL_8:
      v7 = -2147467261;
      goto LABEL_16;
    }
  }
  else if ( *((_DWORD *)this + 9) != 2 )
  {
    v7 = -2147217407;
    goto LABEL_16;
  }
  v7 = ChangeApplicationServices::ValidateIdParameters(v6, (ChangeApplicationServices *)((char *)this + 40), a2);
  if ( v7 >= 0 )
  {
    if ( !a3
      || (v7 = ChangeApplicationServices::ValidateIdParameters(v8, (ChangeApplicationServices *)((char *)this + 40), a3),
          v7 >= 0) )
    {
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 80, a2);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 88, a3);
    }
  }
  v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v6 != (ChangeApplicationServices *)&WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v6 + 2),
      23,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::SetDestinationKnowledge",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004a7f0  push    rbx
0x18004a7f2  push    rbp
0x18004a7f3  push    rsi
0x18004a7f4  push    rdi
0x18004a7f5  push    r14
0x18004a7f7  push    r15
0x18004a7f9  sub     rsp, 38h
0x18004a7fd  mov     rdi, r8
0x18004a800  mov     rbp, rdx
0x18004a803  mov     rsi, rcx
0x18004a806  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a80d  lea     r15, WPP_GLOBAL_Control
0x18004a814  cmp     rcx, r15
0x18004a817  jz      short loc_18004A848
0x18004a819  test    byte ptr [rcx+1Ch], 80h
0x18004a81d  jz      short loc_18004A848
0x18004a81f  cmp     byte ptr [rcx+19h], 5
0x18004a823  jb      short loc_18004A848
0x18004a825  mov     rcx, [rcx+10h]
0x18004a829  lea     r9, aChangeapplicat_38; "ChangeApplicationServices::SetDestinati"...
0x18004a830  mov     edx, 16h
0x18004a835  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a83c  call    WPP_SF_s
0x18004a841  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004a848  test    rbp, rbp
0x18004a84b  jz      short loc_18004A858
0x18004a84d  cmp     dword ptr [rsi+24h], 3
0x18004a851  jnz     short loc_18004A85F
0x18004a853  test    rdi, rdi
0x18004a856  jnz     short loc_18004A86C
0x18004a858  mov     ebx, 80004003h
0x18004a85d  jmp     short loc_18004A8B4
0x18004a85f  cmp     dword ptr [rsi+24h], 2
0x18004a863  jz      short loc_18004A86C
0x18004a865  mov     ebx, 80041001h
0x18004a86a  jmp     short loc_18004A8B4
0x18004a86c  mov     r8, rbp; struct ISyncKnowledge *
0x18004a86f  lea     rdx, [rsi+28h]; struct IdDescription *
0x18004a873  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x18004a878  mov     ebx, eax
0x18004a87a  test    eax, eax
0x18004a87c  js      short loc_18004A8AD
0x18004a87e  test    rdi, rdi
0x18004a881  jz      short loc_18004A895
0x18004a883  mov     r8, rdi; struct ISyncKnowledge *
0x18004a886  lea     rdx, [rsi+28h]; struct IdDescription *
0x18004a88a  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x18004a88f  mov     ebx, eax
0x18004a891  test    eax, eax
0x18004a893  js      short loc_18004A8AD
0x18004a895  lea     rcx, [rsi+50h]
0x18004a899  mov     rdx, rbp
0x18004a89c  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004a8a1  lea     rcx, [rsi+58h]
0x18004a8a5  mov     rdx, rdi
0x18004a8a8  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004a8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a8b4  cmp     rcx, r15
0x18004a8b7  jz      short loc_18004A8E5
0x18004a8b9  test    byte ptr [rcx+1Ch], 80h
0x18004a8bd  jz      short loc_18004A8E5
0x18004a8bf  cmp     byte ptr [rcx+19h], 5
0x18004a8c3  jb      short loc_18004A8E5
0x18004a8c5  mov     rcx, [rcx+10h]
0x18004a8c9  lea     r9, aChangeapplicat_38; "ChangeApplicationServices::SetDestinati"...
0x18004a8d0  mov     edx, 17h
0x18004a8d5  mov     [rsp+68h+var_48], ebx
0x18004a8d9  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a8e0  call    WPP_SF_sD
0x18004a8e5  mov     eax, ebx
0x18004a8e7  add     rsp, 38h
0x18004a8eb  pop     r15
0x18004a8ed  pop     r14
0x18004a8ef  pop     rdi
0x18004a8f0  pop     rsi
0x18004a8f1  pop     rbp
0x18004a8f2  pop     rbx
0x18004a8f3  retn
```
