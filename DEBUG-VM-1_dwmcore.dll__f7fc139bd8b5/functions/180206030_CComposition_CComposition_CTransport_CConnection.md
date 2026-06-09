# CComposition::CComposition(CTransport *,CConnection *)

- ea: `0x180206030`
- end: `0x180206589`
- name: `??0CComposition@@IEAA@PEAVCTransport@@PEAVCConnection@@@Z`
- size: `1369`
- prototype: `CComposition *__fastcall(CComposition *__hidden this, struct CTransport *, struct CConnection *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180205fbc`

## callees

- `0x1800341e0`
- `0x18005d940`
- `0x1800d57f0`
- `0x1801e8168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802061a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180206344`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1802061a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180206344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020655b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18020655b`

## pseudocode

```c
CComposition *__fastcall CComposition::CComposition(CComposition *this, struct CTransport *a2, struct CConnection *a3)
{
  LARGE_INTEGER v6; // rax
  _QWORD *v7; // rax
  CComposition *result; // rax

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CComposition::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = (char *)this + 48;
  *((_QWORD *)this + 4) = (char *)this + 48;
  *((_QWORD *)this + 5) = (char *)this + 64;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = -1;
  *((_DWORD *)this + 63) = 0;
  *((_OWORD *)this + 16) = 0;
  *((_OWORD *)this + 17) = 0;
  *((_QWORD *)this + 36) = 0;
  CScheduler::s_vBlankWaitTimeoutMonitorOffMs = CCommonRegistryData::vBlankWaitTimeoutMonitorOffMs;
  v6 = g_qpcFrequency;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = (char *)this + 344;
  *((_QWORD *)this + 41) = (char *)this + 344;
  *((_QWORD *)this + 42) = (char *)this + 360;
  CScheduler::s_maxVBlankTimeQPC.QuadPart = 80 * v6.QuadPart / 1000;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 9);
  *((_QWORD *)this + 50) = (char *)this + 424;
  *((_QWORD *)this + 51) = (char *)this + 424;
  *((_QWORD *)this + 52) = (char *)this + 552;
  *((_QWORD *)this + 69) = (char *)this + 576;
  *((_QWORD *)this + 70) = (char *)this + 576;
  *((_QWORD *)this + 71) = (char *)this + 608;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  CMmcssTask::CMmcssTask((CComposition *)((char *)this + 728));
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_DWORD *)this + 214) = 0;
  *((_QWORD *)this + 110) = 0;
  *((_DWORD *)this + 216) = 1;
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_DWORD *)this + 230) = 0;
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_DWORD *)this + 238) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_DWORD *)this + 246) = 0;
  *((_DWORD *)this + 1287) = -1;
  *((_DWORD *)this + 1286) = -1;
  *((_DWORD *)this + 251) = -1;
  *((_DWORD *)this + 250) = -1;
  *((_QWORD *)this + 642) = g_qpcFrequency.QuadPart / 60;
  *((_BYTE *)this + 5656) = 0;
  *((_QWORD *)this + 708) = a2;
  *((_QWORD *)this + 709) = a3;
  *((_QWORD *)this + 710) = 0;
  *((_QWORD *)this + 711) = 0;
  *((_QWORD *)this + 712) = 0;
  *((_DWORD *)this + 1426) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 5712));
  *((_QWORD *)this + 719) = 0;
  *((_QWORD *)this + 720) = 0;
  *((_QWORD *)this + 721) = 0;
  *((_QWORD *)this + 722) = 0;
  *((_QWORD *)this + 723) = (char *)this + 5808;
  *((_QWORD *)this + 724) = (char *)this + 5808;
  *((_QWORD *)this + 725) = (char *)this + 5872;
  *((_QWORD *)this + 734) = 0;
  *((_QWORD *)this + 735) = 0;
  *((_QWORD *)this + 736) = 0;
  *((_DWORD *)this + 1474) = 0;
  *((_QWORD *)this + 738) = (char *)this + 5936;
  *((_QWORD *)this + 739) = (char *)this + 5936;
  *((_DWORD *)this + 1480) = 1;
  *(_QWORD *)((char *)this + 5924) = 1;
  *((_QWORD *)this + 743) = 0;
  *((_QWORD *)this + 744) = 0;
  *((_QWORD *)this + 745) = 0;
  *((_QWORD *)this + 746) = (char *)this + 6000;
  *((_QWORD *)this + 747) = (char *)this + 6000;
  *((_DWORD *)this + 1496) = 16;
  *(_QWORD *)((char *)this + 5988) = 16;
  *((_QWORD *)this + 766) = 0;
  *((_QWORD *)this + 767) = 0;
  *((_QWORD *)this + 768) = 0;
  *((_QWORD *)this + 769) = 0;
  *((_QWORD *)this + 770) = 0;
  *((_QWORD *)this + 771) = 0;
  *((_QWORD *)this + 772) = 0;
  *((_QWORD *)this + 773) = 0;
  *((_DWORD *)this + 1548) = 0;
  *((_QWORD *)this + 775) = 0;
  *((_QWORD *)this + 776) = 0;
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
  *v7 = v7;
  v7[1] = v7;
  *((_QWORD *)this + 775) = v7;
  *((_QWORD *)this + 777) = 0;
  *((_QWORD *)this + 778) = 0;
  *((_QWORD *)this + 779) = 0;
  *((_QWORD *)this + 780) = 7;
  *((_QWORD *)this + 781) = 8;
  *((_DWORD *)this + 1548) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<IUnknown *>>,std::_Iterator_base0>>>::_Assign_grow(
    (char *)this + 6216,
    16,
    *((_QWORD *)this + 775));
  *((_QWORD *)this + 784) = 0;
  *((_QWORD *)this + 783) = 0;
  *((_QWORD *)this + 785) = 0;
  *((_DWORD *)this + 1593) = 0;
  *((_QWORD *)this + 799) = 0;
  *((_QWORD *)this + 800) = 0;
  *((_BYTE *)this + 6408) = 0;
  *((_QWORD *)this + 802) = 0;
  *((_QWORD *)this + 803) = 0;
  *((_QWORD *)this + 804) = 0;
  *((_QWORD *)this + 805) = 0;
  *((_DWORD *)this + 1612) = 0;
  *(_QWORD *)((char *)this + 6452) = 1;
  *((_DWORD *)this + 1615) = 0;
  *((_WORD *)this + 3232) = 0;
  *((_BYTE *)this + 6466) = 0;
  *((_DWORD *)this + 1617) = 37120;
  *((_QWORD *)this + 809) = 37120;
  *((_QWORD *)this + 810) = 0;
  *((_QWORD *)this + 811) = 0;
  *((_QWORD *)this + 812) = 0;
  *((_QWORD *)this + 813) = 0;
  *((_QWORD *)this + 814) = 0;
  CComposition::s_compositionThreadId = GetCurrentThreadId();
  CMILRefCountImpl::AddReference((CComposition *)((char *)this + 8));
  result = this;
  g_pFrameId = (unsigned __int64 *)((char *)this + 880);
  return result;
}

```

## disassembly

```asm
0x180206030  push    rbx
0x180206032  push    rbp
0x180206033  push    rsi
0x180206034  push    rdi
0x180206035  push    r13
0x180206037  push    r14
0x180206039  push    r15
0x18020603b  sub     rsp, 20h
0x18020603f  xor     r13d, r13d
0x180206042  lea     rax, ??_7CComposition@@6B@; const CComposition::`vftable'
0x180206049  mov     [rcx+8], r13d
0x18020604d  mov     r15, rcx
0x180206050  mov     [rcx], rax
0x180206053  mov     rbx, rdx
0x180206056  mov     [rcx+10h], r13
0x18020605a  lea     rax, [rcx+30h]
0x18020605e  mov     [rcx+18h], rax
0x180206062  xorps   xmm0, xmm0
0x180206065  mov     [rcx+20h], rax
0x180206069  or      ebp, 0FFFFFFFFh
0x18020606c  lea     rax, [rcx+40h]
0x180206070  mov     rdi, r8
0x180206073  mov     [rcx+28h], rax
0x180206077  xor     eax, eax
0x180206079  mov     [rcx+40h], r13
0x18020607d  mov     [rcx+48h], r13
0x180206081  mov     [rcx+50h], r13
0x180206085  mov     [rcx+58h], r13
0x180206089  mov     [rcx+60h], r13
0x18020608d  mov     [rcx+68h], r13
0x180206091  mov     [rcx+70h], r13
0x180206095  mov     [rcx+78h], r13
0x180206099  mov     [rcx+80h], r13
0x1802060a0  mov     [rcx+88h], r13d
0x1802060a7  mov     [rcx+90h], r13
0x1802060ae  mov     [rcx+98h], r13
0x1802060b5  mov     [rcx+0A0h], r13
0x1802060bc  mov     [rcx+0A8h], r13
0x1802060c3  mov     [rcx+0B0h], r13
0x1802060ca  mov     [rcx+0B8h], r13
0x1802060d1  mov     [rcx+0C0h], r13
0x1802060d8  mov     [rcx+0C8h], r13
0x1802060df  mov     [rcx+0D0h], r13
0x1802060e6  mov     [rcx+0D8h], r13
0x1802060ed  mov     [rcx+0E0h], r13d
0x1802060f4  mov     [rcx+0E8h], r13
0x1802060fb  mov     [rcx+0F0h], r13
0x180206102  mov     [rcx+0F8h], ebp
0x180206108  mov     [rcx+0FCh], r13d
0x18020610f  movups  xmmword ptr [rcx+100h], xmm0
0x180206116  movups  xmmword ptr [rcx+110h], xmm0
0x18020611d  mov     [rcx+120h], rax
0x180206124  mov     eax, cs:?vBlankWaitTimeoutMonitorOffMs@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::vBlankWaitTimeoutMonitorOffMs
0x18020612a  mov     cs:?s_vBlankWaitTimeoutMonitorOffMs@CScheduler@@2KA, eax; ulong CScheduler::s_vBlankWaitTimeoutMonitorOffMs
0x180206130  mov     rax, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x180206137  mov     [r15+128h], r13
0x18020613e  mov     [r15+130h], r13
0x180206145  mov     [r15+138h], r13
0x18020614c  lea     rcx, [rax+rax*4]
0x180206150  mov     rax, 20C49BA5E353F7CFh
0x18020615a  shl     rcx, 4
0x18020615e  imul    rcx
0x180206161  lea     rcx, [r15+168h]; lpCriticalSection
0x180206168  sar     rdx, 7
0x18020616c  mov     rax, rdx
0x18020616f  shr     rax, 3Fh
0x180206173  add     rdx, rax
0x180206176  lea     rax, [r15+158h]
0x18020617d  mov     [r15+140h], rax
0x180206184  mov     [r15+148h], rax
0x18020618b  lea     rax, [r15+168h]
0x180206192  mov     [r15+150h], rax
0x180206199  mov     cs:?s_maxVBlankTimeQPC@CScheduler@@1T_LARGE_INTEGER@@A, rdx; _LARGE_INTEGER CScheduler::s_maxVBlankTimeQPC
0x1802061a0  call    cs:__imp_InitializeCriticalSection
0x1802061a6  lea     rax, [r15+1A8h]
0x1802061ad  mov     [r15+190h], rax
0x1802061b4  mov     [r15+198h], rax
0x1802061bb  lea     rax, [r15+228h]
0x1802061c2  mov     [r15+1A0h], rax
0x1802061c9  lea     rax, [r15+240h]
0x1802061d0  mov     [r15+228h], rax
0x1802061d7  mov     [r15+230h], rax
0x1802061de  lea     rax, [r15+260h]
0x1802061e5  mov     [r15+238h], rax
0x1802061ec  mov     [r15+260h], r13
0x1802061f3  mov     [r15+290h], r13
0x1802061fa  mov     [r15+298h], r13
0x180206201  mov     [r15+2A0h], r13
0x180206208  mov     [r15+2B0h], r13
0x18020620f  mov     [r15+2B8h], r13
0x180206216  lea     rcx, [r15+2D8h]; this
0x18020621d  mov     [r15+2C0h], r13
0x180206224  mov     [r15+2C8h], r13
0x18020622b  mov     [r15+2D0h], r13
0x180206232  call    ??0CMmcssTask@@QEAA@XZ; CMmcssTask::CMmcssTask(void)
0x180206237  mov     [r15+340h], r13
0x18020623e  lea     rsi, [r15+370h]
0x180206245  mov     [r15+348h], r13
0x18020624c  lea     rcx, [r15+1650h]; lpCriticalSection
0x180206253  mov     [r15+350h], r13
0x18020625a  mov     rax, 8888888888888889h
0x180206264  mov     [r15+358h], r13d
0x18020626b  mov     [rsi], r13
0x18020626e  mov     dword ptr [r15+360h], 1
0x180206279  mov     [r15+378h], r13
0x180206280  mov     [r15+380h], r13
0x180206287  mov     [r15+388h], r13
0x18020628e  mov     [r15+390h], r13
0x180206295  mov     [r15+398h], r13d
0x18020629c  mov     [r15+3A0h], r13
0x1802062a3  mov     [r15+3A8h], r13
0x1802062aa  mov     [r15+3B0h], r13
0x1802062b1  mov     [r15+3B8h], r13d
0x1802062b8  mov     [r15+3C0h], r13
0x1802062bf  mov     [r15+3C8h], r13
0x1802062c6  mov     [r15+3D0h], r13
0x1802062cd  mov     [r15+3D8h], r13d
0x1802062d4  mov     [r15+141Ch], ebp
0x1802062db  mov     [r15+1418h], ebp
0x1802062e2  mov     [r15+3ECh], ebp
0x1802062e9  mov     [r15+3E8h], ebp
0x1802062f0  imul    qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1802062f7  add     rdx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1802062fe  sar     rdx, 5
0x180206302  mov     rax, rdx
0x180206305  shr     rax, 3Fh
0x180206309  add     rdx, rax
0x18020630c  mov     [r15+1410h], rdx
0x180206313  mov     [r15+1618h], r13b
0x18020631a  mov     [r15+1620h], rbx
0x180206321  mov     [r15+1628h], rdi
0x180206328  mov     [r15+1630h], r13
0x18020632f  mov     [r15+1638h], r13
0x180206336  mov     [r15+1640h], r13
0x18020633d  mov     [r15+1648h], r13d
0x180206344  call    cs:__imp_InitializeCriticalSection
0x18020634a  mov     [r15+1678h], r13
0x180206351  lea     rax, [r15+16B0h]
0x180206358  mov     [r15+1680h], r13
0x18020635f  lea     ebx, [r13+10h]
0x180206363  mov     [r15+1688h], r13
0x18020636a  mov     [r15+1690h], r13
0x180206371  mov     [r15+1698h], rax
0x180206378  mov     [r15+16A0h], rax
0x18020637f  lea     rax, [r15+16F0h]
0x180206386  mov     [r15+16A8h], rax
0x18020638d  lea     rax, [r15+1730h]
0x180206394  mov     [r15+16F0h], r13
0x18020639b  mov     [r15+16F8h], r13
0x1802063a2  mov     [r15+1700h], r13
0x1802063a9  mov     [r15+1708h], r13d
0x1802063b0  mov     [r15+1710h], rax
0x1802063b7  mov     [r15+1718h], rax
0x1802063be  lea     rax, [r15+1770h]
0x1802063c5  mov     dword ptr [r15+1720h], 1
0x1802063d0  mov     qword ptr [r15+1724h], 1
0x1802063db  mov     [r15+1738h], r13
0x1802063e2  mov     [r15+1740h], r13
0x1802063e9  mov     [r15+1748h], r13
0x1802063f0  mov     [r15+1750h], rax
0x1802063f7  mov     [r15+1758h], rax
0x1802063fe  mov     [r15+1760h], ebx
0x180206405  mov     [r15+1764h], rbx
0x18020640c  mov     [r15+17F0h], r13
0x180206413  mov     [r15+17F8h], r13
0x18020641a  mov     [r15+1800h], r13
0x180206421  mov     [r15+1808h], r13
0x180206428  mov     [r15+1810h], r13
0x18020642f  mov     [r15+1818h], r13
0x180206436  mov     [r15+1820h], r13
0x18020643d  mov     [r15+1828h], r13
0x180206444  lea     ecx, [rbx+28h]; dwBytes
0x180206447  mov     [r15+1830h], r13d
0x18020644e  mov     [r15+1838h], r13
0x180206455  mov     [r15+1840h], r13
0x18020645c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180206461  lea     rcx, [r15+1848h]
0x180206468  mov     edx, ebx
0x18020646a  mov     [rax], rax
0x18020646d  mov     [rax+8], rax
0x180206471  mov     [r15+1838h], rax
0x180206478  mov     [rcx], r13
0x18020647b  mov     [rcx+8], r13
0x18020647f  mov     [rcx+10h], r13
0x180206483  mov     qword ptr [r15+1860h], 7
0x18020648e  mov     qword ptr [r15+1868h], 8
0x180206499  mov     dword ptr [r15+1830h], 3F800000h
0x1802064a4  mov     r8, [r15+1838h]
0x1802064ab  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAUIUnknown@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAUIUnknown@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<IUnknown *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<IUnknown *>>,std::_Iterator_base0>)
0x1802064b0  mov     [r15+1880h], r13
0x1802064b7  mov     eax, 9100h
0x1802064bc  mov     [r15+1878h], r13
0x1802064c3  mov     [r15+1888h], r13
0x1802064ca  mov     [r15+18E4h], r13d
0x1802064d1  mov     [r15+18F8h], r13
0x1802064d8  mov     [r15+1900h], r13
0x1802064df  mov     [r15+1908h], r13b
0x1802064e6  mov     [r15+1910h], r13
0x1802064ed  mov     [r15+1918h], r13
0x1802064f4  mov     [r15+1920h], r13
0x1802064fb  mov     [r15+1928h], r13
0x180206502  mov     [r15+1930h], r13d
0x180206509  mov     qword ptr [r15+1934h], 1
0x180206514  mov     [r15+193Ch], r13d
0x18020651b  mov     [r15+1940h], r13w
0x180206523  mov     [r15+1942h], r13b
0x18020652a  mov     [r15+1944h], eax
0x180206531  mov     [r15+1948h], rax
0x180206538  mov     [r15+1950h], r13
0x18020653f  mov     [r15+1958h], r13
0x180206546  mov     [r15+1960h], r13
0x18020654d  mov     [r15+1968h], r13
0x180206554  mov     [r15+1970h], r13
0x18020655b  call    cs:__imp_GetCurrentThreadId
0x180206561  lea     rcx, [r15+8]; this
0x180206565  mov     cs:?s_compositionThreadId@CComposition@@0KA, eax; ulong CComposition::s_compositionThreadId
0x18020656b  call    ?AddReference@CMILRefCountImpl@@IEAAKXZ; CMILRefCountImpl::AddReference(void)
0x180206570  mov     rax, r15
0x180206573  mov     cs:?g_pFrameId@@3PEA_KEA, rsi; unsigned __int64 * g_pFrameId
0x18020657a  add     rsp, 20h
0x18020657e  pop     r15
0x180206580  pop     r14
0x180206582  pop     r13
0x180206584  pop     rdi
0x180206585  pop     rsi
0x180206586  pop     rbp
0x180206587  pop     rbx
0x180206588  retn
```
