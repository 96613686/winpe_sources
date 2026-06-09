# APP_HOST_SERVICE::APP_HOST_SERVICE(void)

- ea: `0x180005290`
- end: `0x18000543f`
- name: `??0APP_HOST_SERVICE@@QEAA@XZ`
- size: `431`
- prototype: `APP_HOST_SERVICE *__fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180006ad0`

## callees

- `0x1800077e8`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x1800052e3`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x1800052e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
APP_HOST_SERVICE *__fastcall APP_HOST_SERVICE::APP_HOST_SERVICE(APP_HOST_SERVICE *this)
{
  *(_QWORD *)this = &APP_HOST_SERVICE::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = &MULTI_WORK_QUEUE::`vftable';
  *((_QWORD *)this + 4) = 1364350797;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  EVENT_LOG::EVENT_LOG((APP_HOST_SERVICE *)((char *)this + 136), L"APPHOSTSVC");
  *((_DWORD *)this + 35) = 0;
  *((_QWORD *)this + 18) = 1262702412;
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 34) = &SID_MAPPER::`vftable'{for `INativeChangeListener'};
  *((_QWORD *)this + 35) = &SID_MAPPER::`vftable'{for `MULTI_WORK_DISPATCH'};
  *((_DWORD *)this + 73) = 1;
  *((_QWORD *)this + 37) = 0;
  APP_POOL_HASH_MAPPER::APP_POOL_HASH_MAPPER((APP_HOST_SERVICE *)((char *)this + 304));
  *((_DWORD *)this + 114) = 0;
  *((_DWORD *)this + 115) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 72) = 1296320851;
  *((_QWORD *)this + 59) = &CONFIG_HISTORY::`vftable'{for `INativeChangeListener'};
  *((_QWORD *)this + 60) = &CONFIG_HISTORY::`vftable'{for `MULTI_WORK_DISPATCH'};
  *(_QWORD *)((char *)this + 492) = 1;
  *((_DWORD *)this + 125) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 1;
  *((_QWORD *)this + 66) = 0;
  *((_DWORD *)this + 134) &= 0xFFFFFFFC;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_DWORD *)this + 122) = 1397245507;
  *((_DWORD *)this + 152) = 1;
  *((_DWORD *)this + 3) = 1;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 32;
  *((_DWORD *)this + 53) = 1;
  *((_QWORD *)this + 27) = 7;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 66) = 0;
  *((_DWORD *)this + 2) = 1448300609;
  return this;
}

```

## disassembly

```asm
0x180005290  mov     [rsp+arg_10], rbx
0x180005295  mov     [rsp+arg_0], rcx
0x18000529a  push    rbp
0x18000529b  push    rsi
0x18000529c  push    rdi
0x18000529d  sub     rsp, 20h
0x1800052a1  mov     rdi, rcx
0x1800052a4  lea     rax, ??_7APP_HOST_SERVICE@@6B@; const APP_HOST_SERVICE::`vftable'
0x1800052ab  mov     [rcx], rax
0x1800052ae  xor     ebp, ebp
0x1800052b0  mov     [rcx+10h], rbp
0x1800052b4  lea     rax, ??_7MULTI_WORK_QUEUE@@6B@; const MULTI_WORK_QUEUE::`vftable'
0x1800052bb  mov     [rcx+18h], rax
0x1800052bf  mov     qword ptr [rcx+20h], 5152574Dh
0x1800052c7  mov     [rcx+70h], ebp
0x1800052ca  mov     [rcx+78h], rbp
0x1800052ce  mov     [rcx+80h], rbp
0x1800052d5  add     rcx, 88h
0x1800052dc  lea     rdx, aApphostsvc; "APPHOSTSVC"
0x1800052e3  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x1800052e9  mov     [rdi+8Ch], ebp
0x1800052ef  mov     qword ptr [rdi+90h], 4B434F4Ch
0x1800052fa  mov     [rdi+0C0h], ebp
0x180005300  lea     rbx, [rdi+110h]
0x180005307  lea     rax, ??_7SID_MAPPER@@6BINativeChangeListener@@@; const SID_MAPPER::`vftable'{for `INativeChangeListener'}
0x18000530e  mov     [rbx], rax
0x180005311  lea     rax, ??_7SID_MAPPER@@6BMULTI_WORK_DISPATCH@@@; const SID_MAPPER::`vftable'{for `MULTI_WORK_DISPATCH'}
0x180005318  mov     [rbx+8], rax
0x18000531c  lea     esi, [rbp+1]
0x18000531f  mov     [rbx+14h], esi
0x180005322  mov     [rbx+18h], rbp
0x180005326  lea     rcx, [rbx+20h]; this
0x18000532a  call    ??0APP_POOL_HASH_MAPPER@@QEAA@XZ; APP_POOL_HASH_MAPPER::APP_POOL_HASH_MAPPER(void)
0x18000532f  mov     [rbx+0B8h], ebp
0x180005335  mov     [rbx+0BCh], ebp
0x18000533b  mov     [rbx+0C0h], rbp
0x180005342  mov     dword ptr [rbx+10h], 4D444953h
0x180005349  lea     rax, ??_7CONFIG_HISTORY@@6BINativeChangeListener@@@; const CONFIG_HISTORY::`vftable'{for `INativeChangeListener'}
0x180005350  mov     [rdi+1D8h], rax
0x180005357  lea     rax, ??_7CONFIG_HISTORY@@6BMULTI_WORK_DISPATCH@@@; const CONFIG_HISTORY::`vftable'{for `MULTI_WORK_DISPATCH'}
0x18000535e  mov     [rdi+1E0h], rax
0x180005365  mov     [rdi+1ECh], esi
0x18000536b  mov     [rdi+1F0h], ebp
0x180005371  mov     [rdi+1F4h], ebp
0x180005377  mov     [rdi+1F8h], rbp
0x18000537e  mov     [rdi+200h], rbp
0x180005385  mov     [rdi+208h], rsi
0x18000538c  mov     [rdi+210h], rbp
0x180005393  and     dword ptr [rdi+218h], 0FFFFFFFCh
0x18000539a  mov     [rdi+220h], rbp
0x1800053a1  mov     [rdi+228h], rbp
0x1800053a8  mov     [rdi+230h], rbp
0x1800053af  mov     [rdi+238h], rbp
0x1800053b6  mov     [rdi+240h], rbp
0x1800053bd  mov     [rdi+248h], rbp
0x1800053c4  mov     [rdi+250h], rbp
0x1800053cb  mov     [rdi+258h], rbp
0x1800053d2  mov     dword ptr [rdi+1E8h], 53484643h
0x1800053dc  mov     [rdi+260h], esi
0x1800053e2  mov     [rdi+0Ch], esi
0x1800053e5  mov     [rdi+0C8h], rbp
0x1800053ec  mov     dword ptr [rdi+0D0h], 20h ; ' '
0x1800053f6  mov     [rdi+0D4h], esi
0x1800053fc  mov     qword ptr [rdi+0D8h], 7
0x180005407  mov     [rdi+0E0h], rbp
0x18000540e  mov     [rdi+0E8h], ebp
0x180005414  mov     [rdi+0F8h], rbp
0x18000541b  mov     [rdi+100h], rbp
0x180005422  mov     [rdi+108h], ebp
0x180005428  mov     dword ptr [rdi+8], 56535041h
0x18000542f  mov     rax, rdi
0x180005432  mov     rbx, [rsp+38h+arg_10]
0x180005437  add     rsp, 20h
0x18000543b  pop     rdi
0x18000543c  pop     rsi
0x18000543d  pop     rbp
0x18000543e  retn
```
