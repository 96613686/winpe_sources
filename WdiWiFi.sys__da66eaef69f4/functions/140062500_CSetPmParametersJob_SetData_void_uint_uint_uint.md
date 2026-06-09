# CSetPmParametersJob::SetData(void *,uint,uint *,uint *)

- ea: `0x140062500`
- end: `0x1400626da`
- name: `?SetData@CSetPmParametersJob@@MEAAHPEAXIPEAI1@Z`
- size: `474`
- prototype: `__int64 __fastcall(CSetPmParametersJob *__hidden this, void *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400122e0`
- `0x14002aa28`
- `0x14002c5d8`
- `0x140034e04`
- `0x140062500`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400625c3`
- `ntoskrnl!RtlCompareMemory` at `0x1400625c3`

## pseudocode

```c
__int64 __fastcall CSetPmParametersJob::SetData(
        CSetPmParametersJob *this,
        _DWORD *a2,
        unsigned int a3,
        unsigned int *a4)
{
  _DWORD *v5; // rbp
  struct CPort *PortFromNdisPortNumber; // rax
  struct CPort *v8; // rsi
  unsigned int v9; // edi
  char v10; // al
  _BYTE v12[24]; // [rsp+40h] [rbp-58h] BYREF

  memset(v12, 0, 20);
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      10,
      (__int64)WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( this->CSimpleSetOidJob::COidJobBase::m_NdisPortNumber )
  {
    v9 = -1073741637;
  }
  else
  {
    PortFromNdisPortNumber = CAdapter::GetPortFromNdisPortNumber(this->m_pAdapter, 0);
    v8 = PortFromNdisPortNumber;
    if ( PortFromNdisPortNumber && a3 >= 0x14 )
    {
      *(_OWORD *)&PortFromNdisPortNumber->m_NdisPmParameters.Header.Type = 0;
      PortFromNdisPortNumber->m_NdisPmParameters.MediaSpecificWakeUpEvents = 0;
      v9 = 0;
      *(_OWORD *)&PortFromNdisPortNumber->m_NdisPmParameters.Header.Type = *(_OWORD *)v5;
      PortFromNdisPortNumber->m_NdisPmParameters.MediaSpecificWakeUpEvents = v5[4];
      if ( RtlCompareMemory(&v12[4], &PortFromNdisPortNumber->m_NdisPmParameters.EnabledWoLPacketPatterns, 0x10u) == 16 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            1,
            11,
            (__int64)WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids);
        }
        v10 = 0;
      }
      else
      {
        v10 = 1;
      }
      v8->m_bValidPmParameters = v10;
    }
    else
    {
      v9 = -1073741811;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      this->m_ActivityId,
      12,
      (__int64)WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids,
      (char)this,
      this->m_ActivityId,
      v9,
      *(_OWORD *)v12,
      *(_QWORD *)&v12[16]);
  }
  return v9;
}

```

## disassembly

```asm
0x140062500  push    rbx
0x140062502  push    rbp
0x140062503  push    rsi
0x140062504  push    rdi
0x140062505  push    r12
0x140062507  push    r14
0x140062509  push    r15
0x14006250b  sub     rsp, 60h
0x14006250f  mov     rax, cs:__security_cookie
0x140062516  xor     rax, rsp
0x140062519  mov     [rsp+98h+var_40], rax
0x14006251e  xor     r14d, r14d
0x140062521  xorps   xmm0, xmm0
0x140062524  xor     eax, eax
0x140062526  mov     [rsp+98h+var_58], r14b
0x14006252b  movups  [rsp+98h+Source1], xmm0
0x140062530  mov     dword ptr [rsp+98h+Source1+0Fh], eax
0x140062534  mov     edi, r8d
0x140062537  mov     rbp, rdx
0x14006253a  mov     rbx, rcx
0x14006253d  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140062544  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006254b  lea     r12, WPP_984157a2d4d43e2348b6e3f75fb3939d_Traceguids
0x140062552  jnz     loc_140062628
0x140062558  cmp     [rbx+218h], r14d
0x14006255f  jnz     loc_140062671
0x140062565  mov     rcx, [rbx+200h]; this
0x14006256c  xor     edx, edx; unsigned int
0x14006256e  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x140062573  mov     rsi, rax
0x140062576  test    rax, rax
0x140062579  jz      loc_140062667
0x14006257f  cmp     edi, 14h
0x140062582  jb      loc_140062667
0x140062588  xorps   xmm0, xmm0
0x14006258b  lea     rdx, [rsi+3D4h]; Source2
0x140062592  movups  xmmword ptr [rsi+3D0h], xmm0
0x140062599  xor     eax, eax
0x14006259b  lea     rcx, [rsp+98h+Source1+3]; Source1
0x1400625a0  mov     [rsi+3E0h], eax
0x1400625a6  mov     r8d, 10h; Length
0x1400625ac  movups  xmm0, xmmword ptr [rbp+0]
0x1400625b0  mov     edi, r14d
0x1400625b3  movups  xmmword ptr [rsi+3D0h], xmm0
0x1400625ba  mov     eax, [rbp+10h]
0x1400625bd  mov     [rsi+3E0h], eax
0x1400625c3  call    cs:__imp_RtlCompareMemory
0x1400625ca  nop     dword ptr [rax+rax+00h]
0x1400625cf  cmp     rax, 10h
0x1400625d3  jz      loc_14006267B
0x1400625d9  mov     eax, 1
0x1400625de  mov     [rsi+3E4h], al
0x1400625e4  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400625eb  jz      short loc_140062609
0x1400625ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400625f4  cmp     byte ptr [rcx+29h], 5
0x1400625f8  jnb     loc_1400626AD
0x1400625fe  cmp     [rcx+48h], r14w
0x140062603  jnz     loc_1400626AD
0x140062609  mov     eax, edi
0x14006260b  mov     rcx, [rsp+98h+var_40]
0x140062610  xor     rcx, rsp; StackCookie
0x140062613  call    __security_check_cookie
0x140062618  add     rsp, 60h
0x14006261c  pop     r15
0x14006261e  pop     r14
0x140062620  pop     r12
0x140062622  pop     rdi
0x140062623  pop     rsi
0x140062624  pop     rbp
0x140062625  pop     rbx
0x140062626  retn
0x140062628  mov     rcx, cs:WPP_GLOBAL_Control
0x14006262f  cmp     byte ptr [rcx+29h], 5
0x140062633  jnb     short loc_140062640
0x140062635  cmp     [rcx+48h], r14w
0x14006263a  jz      loc_140062558
0x140062640  mov     eax, [rbx+10h]
0x140062643  mov     r9d, 0Ah
0x140062649  mov     rcx, [rcx+40h]
0x14006264d  mov     dl, 5
0x14006264f  mov     [rsp+98h+var_68], eax
0x140062653  mov     [rsp+98h+var_70], rbx
0x140062658  mov     [rsp+98h+var_78], r12
0x14006265d  call    WPP_RECORDER_SF_qD
0x140062662  jmp     loc_140062558
0x140062667  mov     edi, 0C000000Dh
0x14006266c  jmp     loc_1400625E4
0x140062671  mov     edi, 0C00000BBh
0x140062676  jmp     loc_1400625E4
0x14006267b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140062682  jz      short loc_1400626A5
0x140062684  mov     rcx, cs:WPP_GLOBAL_Control
0x14006268b  mov     r9d, 0Bh
0x140062691  mov     dl, 4
0x140062693  mov     [rsp+98h+var_78], r12
0x140062698  mov     rcx, [rcx+40h]
0x14006269c  lea     r8d, [r9-0Ah]
0x1400626a0  call    WPP_RECORDER_SF_
0x1400626a5  mov     al, r14b
0x1400626a8  jmp     loc_1400625DE
0x1400626ad  mov     r8d, [rbx+10h]
0x1400626b1  mov     r9d, 0Ch
0x1400626b7  mov     rcx, [rcx+40h]
0x1400626bb  mov     dl, 5
0x1400626bd  mov     [rsp+98h+var_60], edi
0x1400626c1  mov     [rsp+98h+var_68], r8d
0x1400626c6  mov     [rsp+98h+var_70], rbx
0x1400626cb  mov     [rsp+98h+var_78], r12
0x1400626d0  call    WPP_RECORDER_SF_qDD
0x1400626d5  jmp     loc_140062609
```
