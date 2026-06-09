# VideoFrameImpl::CreateXVP(IMFTransform * *)

- ea: `0x18002007c`
- end: `0x180020246`
- name: `?CreateXVP@VideoFrameImpl@@AEAAJPEAPEAUIMFTransform@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(VideoFrameImpl *__hidden this, struct IMFTransform **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eef4`
- `0x1800227b4`
- `0x180022c1c`
- `0x1800231cc`

## callees

- `0x1800019c0`
- `0x1800134e0`
- `0x18001df58`
- `0x18002007c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800200dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800200dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VideoFrameImpl::CreateXVP(VideoFrameImpl *this, struct IMFTransform **a2)
{
  LPVOID *v4; // r14
  LPVOID *p_ppv; // rcx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rbx
  LPVOID *v11; // rdx
  struct IMFTransform *v12; // rax
  __int64 v13; // rcx
  LPVOID v14; // rcx
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF

  ppv = 0;
  v17 = 0;
  v4 = (LPVOID *)((char *)this + 200);
  p_ppv = &ppv;
  if ( *v4 )
  {
    v7 = 0;
    v11 = v4;
    goto LABEL_18;
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppv);
  v6 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_20;
    v8 = 28;
    goto LABEL_5;
  }
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 64LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v17);
  v6 = v10(v9, &v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( g_wppLevels )
    {
      v8 = 29;
LABEL_5:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids, this, v6);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v17 + 168LL))(v17, &MF_XVP_DISABLE_FRC, 1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v17 + 168LL))(
           v17,
           MF_XVP_CALLER_ALLOCATES_OUTPUT,
           1);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 31;
        goto LABEL_5;
      }
      goto LABEL_20;
    }
    if ( !*((_BYTE *)this + 217) )
    {
LABEL_19:
      v12 = (struct IMFTransform *)ppv;
      ppv = 0;
      *a2 = v12;
      goto LABEL_20;
    }
    v11 = &ppv;
    p_ppv = v4;
LABEL_18:
    Microsoft::WRL::ComPtr<IMFTransform>::operator=(p_ppv, v11);
    goto LABEL_19;
  }
  if ( g_wppLevels )
  {
    v8 = 30;
    goto LABEL_5;
  }
LABEL_20:
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return v7;
}

```

## disassembly

```asm
0x18002007c  mov     [rsp-28h+arg_8], rbx
0x180020081  push    rbp
0x180020082  push    rsi
0x180020083  push    rdi
0x180020084  push    r14
0x180020086  push    r15
0x180020088  mov     rbp, rsp
0x18002008b  sub     rsp, 30h
0x18002008f  mov     r15, rdx
0x180020092  mov     rsi, rcx
0x180020095  mov     [rbp+arg_0], 0
0x18002009d  mov     [rbp+arg_10], 0
0x1800200a5  lea     r14, [rcx+0C8h]
0x1800200ac  lea     rcx, [rbp+arg_0]
0x1800200b0  cmp     qword ptr [r14], 0
0x1800200b4  jnz     loc_1800201DE
0x1800200ba  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800200bf  lea     rax, [rbp+arg_0]
0x1800200c3  mov     [rsp+30h+ppv], rax; ppv
0x1800200c8  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800200cf  xor     edx, edx; pUnkOuter
0x1800200d1  lea     r8d, [rdx+1]; dwClsContext
0x1800200d5  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800200dc  call    cs:__imp_CoCreateInstance
0x1800200e2  mov     ebx, eax
0x1800200e4  test    eax, eax
0x1800200e6  jns     short loc_18002011D
0x1800200e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800200ef  jb      loc_1800201F7
0x1800200f5  mov     edx, 1Ch
0x1800200fa  mov     dword ptr [rsp+30h+ppv], eax
0x1800200fe  mov     r9, rsi
0x180020101  lea     r8, WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids
0x180020108  mov     rcx, cs:WPP_GLOBAL_Control
0x18002010f  mov     rcx, [rcx+10h]
0x180020113  call    WPP_SF_qd
0x180020118  jmp     loc_1800201F7
0x18002011d  mov     rdi, [rbp+arg_0]
0x180020121  mov     rax, [rdi]
0x180020124  mov     rbx, [rax+40h]
0x180020128  lea     rcx, [rbp+arg_10]
0x18002012c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180020131  lea     rdx, [rbp+arg_10]
0x180020135  mov     rcx, rdi
0x180020138  mov     rax, rbx
0x18002013b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020140  mov     ebx, eax
0x180020142  test    eax, eax
0x180020144  jns     short loc_18002015A
0x180020146  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002014d  jb      loc_1800201F7
0x180020153  mov     edx, 1Dh
0x180020158  jmp     short loc_1800200FA
0x18002015a  mov     rcx, [rbp+arg_10]
0x18002015e  mov     rax, [rcx]
0x180020161  mov     r8d, 1
0x180020167  lea     rdx, MF_XVP_DISABLE_FRC
0x18002016e  mov     rax, [rax+0A8h]
0x180020175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002017a  mov     ebx, eax
0x18002017c  test    eax, eax
0x18002017e  jns     short loc_180020193
0x180020180  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020187  jb      short loc_1800201F7
0x180020189  mov     edx, 1Eh
0x18002018e  jmp     loc_1800200FA
0x180020193  mov     rcx, [rbp+arg_10]
0x180020197  mov     rax, [rcx]
0x18002019a  mov     r8d, 1
0x1800201a0  lea     rdx, MF_XVP_CALLER_ALLOCATES_OUTPUT
0x1800201a7  mov     rax, [rax+0A8h]
0x1800201ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201b3  mov     ebx, eax
0x1800201b5  test    eax, eax
0x1800201b7  jns     short loc_1800201CC
0x1800201b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800201c0  jb      short loc_1800201F7
0x1800201c2  mov     edx, 1Fh
0x1800201c7  jmp     loc_1800200FA
0x1800201cc  cmp     byte ptr [rsi+0D9h], 0
0x1800201d3  jz      short loc_1800201E8
0x1800201d5  lea     rdx, [rbp+arg_0]
0x1800201d9  mov     rcx, r14
0x1800201dc  jmp     short loc_1800201E3
0x1800201de  xor     ebx, ebx
0x1800201e0  mov     rdx, r14
0x1800201e3  call    ??4?$ComPtr@UIMFTransform@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMFTransform>::operator=(Microsoft::WRL::ComPtr<IMFTransform> const &)
0x1800201e8  mov     rax, [rbp+arg_0]
0x1800201ec  mov     [rbp+arg_0], 0
0x1800201f4  mov     [r15], rax
0x1800201f7  mov     rcx, [rbp+arg_10]
0x1800201fb  test    rcx, rcx
0x1800201fe  jz      short loc_180020215
0x180020200  mov     [rbp+arg_10], 0
0x180020208  mov     rax, [rcx]
0x18002020b  mov     rax, [rax+10h]
0x18002020f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020214  nop
0x180020215  mov     rcx, [rbp+arg_0]
0x180020219  test    rcx, rcx
0x18002021c  jz      short loc_180020233
0x18002021e  mov     [rbp+arg_0], 0
0x180020226  mov     rax, [rcx]
0x180020229  mov     rax, [rax+10h]
0x18002022d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020232  nop
0x180020233  mov     eax, ebx
0x180020235  mov     rbx, [rsp+30h+arg_8]
0x18002023a  add     rsp, 30h
0x18002023e  pop     r15
0x180020240  pop     r14
0x180020242  pop     rdi
0x180020243  pop     rsi
0x180020244  pop     rbp
0x180020245  retn
```
