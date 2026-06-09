# COutOfProcFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002f60`
- end: `0x1400030ee`
- name: `?CreateInstance@COutOfProcFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(COutOfProcFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x140002f60`
- `0x140006010`

## string_xrefs

- `0x140003045`: `m_pFactoryData->CreateInstance failed!`
- `0x140003093`: `pNewComponent->QueryInterface failed!`

## pseudocode

```c
__int64 __fastcall COutOfProcFactory::CreateInstance(
        COutOfProcFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // eax
  int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  __int64 (__fastcall ***v11)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 (__fastcall ***v13)(_QWORD, const struct _GUID *, void **); // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  if ( !a2
    || *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v7 = (*(__int64 (__fastcall **)(HINSTANCE, struct IUnknown *, _QWORD))(*((_QWORD *)this + 1) + 16LL))(
           COutOfProcFactory::s_hInstance,
           a2,
           &v13);
    if ( v7 >= 0 )
    {
      v7 = (**v13)(v13, a3, a4);
      if ( v7 >= 0
        || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 12;
      v10 = "pNewComponent->QueryInterface failed!";
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 11;
      v10 = "m_pFactoryData->CreateInstance failed!";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v10,
      v7);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids, v6, -2147221232);
  }
  v7 = -2147221232;
LABEL_20:
  v11 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v11)[2])(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140002f60  mov     [rsp+arg_0], rbx
0x140002f65  mov     [rsp+arg_10], rsi
0x140002f6a  push    rdi
0x140002f6b  sub     rsp, 30h
0x140002f6f  mov     [rsp+38h+arg_8], 0
0x140002f78  mov     rsi, r9
0x140002f7b  mov     rdi, r8
0x140002f7e  test    rdx, rdx
0x140002f81  jz      short loc_140002FF1
0x140002f83  mov     rax, [r8]
0x140002f86  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x140002f8d  jnz     short loc_140002F9C
0x140002f8f  mov     rax, [r8+8]
0x140002f93  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x140002f9a  jz      short loc_140002FF1
0x140002f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fa3  lea     rax, WPP_GLOBAL_Control
0x140002faa  cmp     rcx, rax
0x140002fad  jz      short loc_140002FE7
0x140002faf  test    byte ptr [rcx+1Ch], 8
0x140002fb3  jz      short loc_140002FE7
0x140002fb5  cmp     byte ptr [rcx+19h], 2
0x140002fb9  jb      short loc_140002FE7
0x140002fbb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140002fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fc7  lea     r8, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids
0x140002fce  mov     edx, 0Ah
0x140002fd3  mov     dword ptr [rsp+38h+var_18], 80040110h
0x140002fdb  mov     r9d, eax
0x140002fde  mov     rcx, [rcx+10h]
0x140002fe2  call    WPP_SF_Dd
0x140002fe7  mov     ebx, 80040110h
0x140002fec  jmp     loc_1400030BD
0x140002ff1  mov     rax, [rcx+8]
0x140002ff5  lea     r8, [rsp+38h+arg_8]
0x140002ffa  mov     rcx, cs:?s_hInstance@COutOfProcFactory@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * COutOfProcFactory::s_hInstance
0x140003001  mov     rax, [rax+10h]
0x140003005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000300a  mov     ebx, eax
0x14000300c  test    eax, eax
0x14000300e  jns     short loc_14000304E
0x140003010  mov     rcx, cs:WPP_GLOBAL_Control
0x140003017  lea     rax, WPP_GLOBAL_Control
0x14000301e  cmp     rcx, rax
0x140003021  jz      loc_1400030BD
0x140003027  test    byte ptr [rcx+1Ch], 8
0x14000302b  jz      loc_1400030BD
0x140003031  cmp     byte ptr [rcx+19h], 2
0x140003035  jb      loc_1400030BD
0x14000303b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003040  mov     edx, 0Bh
0x140003045  lea     rcx, aMPfactorydataC; "m_pFactoryData->CreateInstance failed!"
0x14000304c  jmp     short loc_14000309A
0x14000304e  mov     rcx, [rsp+38h+arg_8]
0x140003053  mov     r8, rsi
0x140003056  mov     rdx, rdi
0x140003059  mov     rax, [rcx]
0x14000305c  mov     rax, [rax]
0x14000305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003064  mov     ebx, eax
0x140003066  test    eax, eax
0x140003068  jns     short loc_1400030BD
0x14000306a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003071  lea     rax, WPP_GLOBAL_Control
0x140003078  cmp     rcx, rax
0x14000307b  jz      short loc_1400030BD
0x14000307d  test    byte ptr [rcx+1Ch], 8
0x140003081  jz      short loc_1400030BD
0x140003083  cmp     byte ptr [rcx+19h], 2
0x140003087  jb      short loc_1400030BD
0x140003089  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000308e  mov     edx, 0Ch
0x140003093  lea     rcx, aPnewcomponentQ; "pNewComponent->QueryInterface failed!"
0x14000309a  mov     [rsp+38h+var_10], ebx
0x14000309e  lea     r8, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids
0x1400030a5  mov     [rsp+38h+var_18], rcx
0x1400030aa  mov     r9d, eax
0x1400030ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030b4  mov     rcx, [rcx+10h]
0x1400030b8  call    WPP_SF_DsD
0x1400030bd  mov     rcx, [rsp+38h+arg_8]
0x1400030c2  test    rcx, rcx
0x1400030c5  jz      short loc_1400030DC
0x1400030c7  mov     [rsp+38h+arg_8], 0
0x1400030d0  mov     rax, [rcx]
0x1400030d3  mov     rax, [rax+10h]
0x1400030d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030dc  mov     rsi, [rsp+38h+arg_10]
0x1400030e1  mov     eax, ebx
0x1400030e3  mov     rbx, [rsp+38h+arg_0]
0x1400030e8  add     rsp, 30h
0x1400030ec  pop     rdi
0x1400030ed  retn
```
